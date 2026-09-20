# Killing Misbehaving Processes

> Module: **Linux Luminarium / Processess and Jobs** · Challenge: `killing-misbehaving-processes`

`/tmp/flag_fifo` named pipe-ийг эзэмдсэн `/challenge/decoy` процессыг `kill`-ээр зогсоож, дараа нь `/challenge/run`-ийн бичсэн жинхэнэ флагийг уншина.

## Тайлбар

- `decoy` процесс нь `/tmp/flag_fifo` FIFO-д хуурамч флагуудыг тасралтгүй бичиж байдаг тул `/challenge/run`-ийн бичсэн жинхэнэ флаг хогийн дунд дарагдана.
- `ps -ef`-д `hacker 114 113 ... /usr/bin/python3 /challenge/decoy` мөр байсан → PID **114**, `kill 114`.
- Pipe нь **буфертэй**: `kill` хийх үед FIFO дотор аль хэдийн орсон өгөгдөл `cat`-руу цааш урсдаг. Тиймээс устгасны дараа ч хэдэн зуун decoy флаг хэвлэгдсээр байв — хэдэн секунд хүлээх хэрэгтэй.
- Хооронд `/challenge/decoy`-г өөрөө ажиллуулж үзсэн (иймд Python traceback-тай `KeyboardInterrupt` гарсан) — decoy нь энэ урсгалын эх үүсвэр болохыг батлав.
- `cat /tmp/flag_fifo!` → `No such file or directory`: `!`-ийг замын хэсэг болгож бичсэн typo.
- Жинхэнэ флаг нь `.0FNzMDOxwyMwEzM2EzW}` суффикстэй сүүлчийн мөр — decoy флагууд энэ суффиксгүй.
- Доорх session-д decoy флагуудын урсгалыг `...` мөрөөр тасалж тэмдэглэв (үлдсэн нь зөвхөн хуурамч флаг).

## Solution

```console
hacker@processes~killing-misbehaving-processes:~$ ps -ef
UID PID PPID C STIME TTY TIME CMD
root 1 0 0 15:01 ? 00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/
root 7 1 0 15:01 ? 00:00:00 /run/dojo/bin/sleep 6h
root 111 1 0 15:01 ? 00:00:00 sleep 6h
root 112 1 0 15:01 ? 00:00:00 sleep 6h
root 113 1 0 15:01 ? 00:00:00 su -c exec /challenge/decoy > /tmp/flag_fifo hacker
hacker 114 113 0 15:01 ? 00:00:00 /usr/bin/python3 /challenge/decoy
hacker 116 0 0 15:01 pts/0 00:00:00 /nix/store/pkf547jp8a92k4wmxikkyby58w10pysr-bash-interactive-5.3p9/bin/bash /run/dojo/
hacker 122 116 0 15:01 pts/0 00:00:00 /run/dojo/bin/bash --login
hacker 135 1 0 15:01 ? 00:00:00 /nix/store/nzhm2kbnlpp13kwvk192825y8pykhiag-ttyd-1.7.7/bin/ttyd --port 7681 --interfac
hacker 139 135 0 15:01 pts/1 00:00:00 /run/dojo/bin/bash --login
hacker 145 122 0 15:01 pts/0 00:00:00 ps -ef
hacker@processes~killing-misbehaving-processes:~$ kill 114
hacker@processes~killing-misbehaving-processes:~$ /challenge/run
Sending the flag to /tmp/flag_fifo!
^C
hacker@processes~killing-misbehaving-processes:~$ cat /tmp/flag_fifo
pwn.college{P.Yl7PKfpuWpwLl-ycUd88vlR6vzym23oKuLduarx5h29Bj}
pwn.college{wApQ9jcqJuBxmS1h7ZeAt2VT7cXR-LLETgShsbECOnzoeEw}
pwn.college{rfj8VfoYlzk9pu.GjonwoxR6GdRS6fiwyWCZP--bwopYDds}
pwn.college{j7IrrRMeIFMW9X.wVcgfUSsK8.AixmXhuk3gAJrC2o7nyxt}
pwn.college{Y8pXUavW5hOKwAtzY-2PCwRe3sMVLlHy.vlC6v8PTDqaPys}
pwn.college{FdfX6lqM7rbR4Z8NTxCTwLbj8leQWPFkM0cVs0j11oke0XB}
... (буферт үлдсэн 134 decoy флаг цааш урсав) ...
^C
hacker@processes~killing-misbehaving-processes:~$ ^C
hacker@processes~killing-misbehaving-processes:~$ ps -ef
UID PID PPID C STIME TTY TIME CMD
root 1 0 0 15:01 ? 00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/
root 7 1 0 15:01 ? 00:00:00 /run/dojo/bin/sleep 6h
root 111 1 0 15:01 ? 00:00:00 sleep 6h
root 112 1 0 15:01 ? 00:00:00 sleep 6h
hacker 116 0 0 15:01 pts/0 00:00:00 /nix/store/pkf547jp8a92k4wmxikkyby58w10pysr-bash-interactive-5.3p9/bin/bash /run/dojo/
hacker 122 116 0 15:01 pts/0 00:00:00 /run/dojo/bin/bash --login
hacker 135 1 0 15:01 ? 00:00:00 /nix/store/nzhm2kbnlpp13kwvk192825y8pykhiag-ttyd-1.7.7/bin/ttyd --port 7681 --interfac
hacker 139 135 0 15:01 pts/1 00:00:00 /run/dojo/bin/bash --login
hacker 151 122 0 15:02 pts/0 00:00:00 ps -ef
hacker@processes~killing-misbehaving-processes:~$ /challenge/decoy
pwn.college{wmSB7nmyvMO8XDTA0G14ZXPvK8Hfr60XAafHs6dNaRpHpEl}
pwn.college{8FvRHjhWDxugN.wZvgIg79ZL.pmLA0CDzQ9hJNNZD1dTj00}
pwn.college{kHXQP23RrcHZwaAt.bQ.kvqmg2zUI.ZwitkPcPE2gzokb0r}
pwn.college{oEWhgneoRxeLQ6cJjKwexDZaQRQOD5qbf6mrkdWMJ1oqMxs}
pwn.college{7YJZRP5NbXSpVLxT3Ba5azZOx18gVwN91nUe1jcRW6XmOdq}
... (decoy процесс 247 хуурамч флаг хэвлэсээр байв) ...
^CTraceback (most recent call last):
File "/challenge/decoy", line 16, in <module>
time.sleep(0.01)
KeyboardInterrupt

hacker@processes~killing-misbehaving-processes:~$ /challenge/run
Sending the flag to /tmp/flag_fifo!
hacker@processes~killing-misbehaving-processes:~$ cat /tmp/flag_fifo!
cat: '/tmp/flag_fifo!': No such file or directory
hacker@processes~killing-misbehaving-processes:~$ cat /tmp/flag_fifo
pwn.college{IyrDucG0lQpNKuOPrzXsxgRp1MS.0FNzMDOxwyMwEzM2EzW}
^C
```

## Flag

```
pwn.college{IyrDucG0lQpNKuOPrzXsxgRp1MS.0FNzMDOxwyMwEzM2EzW}
```
