# Listing Processes

> Module: **Linux Luminarium / Processess and Jobs** · Challenge: `listing-processes`

`ps`-ээр ажиллаж байгаа процессуудыг жагсааж, санамсаргүй нэр болгож нуусан `/challenge/run`-ийг процессын жагсаалтаас олж шууд ажиллуулна.

## Тайлбар

| Команд | Тайлбар |
|--------|---------|
| `ps` | Зөвхөн одоогийн терминал дээрх процессуудыг хэвлэнэ (`bash` ба `ps` өөрөө) — ихэвчлэн хэрэггүй. |
| `ps -ef` | "Standard" syntax: `-e` — **бүх** процесс, `-f` — бүтэн формат (PPID, аргументтай CMD). |
| `ps aux` | "BSD" syntax: `a` — бүх хэрэглэгчийн, `x` — терминалгүй, `u` — уншихад хялбар багана (%CPU, %MEM). |
| `ps -efww` / `ps auxww` | `w`-г хоёр удаа өгвөл CMD баганыг терминалын өргөнөөр **тайрахгүй**. |

- Процесс бүр PID (process ID), PPID (эцэг процессын PID), TTY (ажиллаж байгаа терминал) болон зарцуулсан CPU хугацаатай байна.
- `ps -ef`-ийн гаралтад `root 110 1 ... /challenge/20924-run-19933` мөр харагдсан — `run`-ийн нуусан нэр нь энэ. Замыг шууд ажиллуулаад флаг гарлаа.
- `ps /challenge/20924-run-19933` гэж бичихэд `error: garbage option` — `ps` нь файлын зам биш, зөвхөн option хүлээж авдаг.

## Solution

```console
hacker@processes~listing-processes:~$ ps -ef
UID PID PPID C STIME TTY TIME CMD
root 1 0 0 14:55 ? 00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/
root 7 1 0 14:55 ? 00:00:00 /run/dojo/bin/sleep 6h
root 110 1 0 14:55 ? 00:00:00 /challenge/20924-run-19933
root 113 110 0 14:55 ? 00:00:00 sleep 6h
hacker 124 1 0 14:55 ? 00:00:00 /nix/store/nzhm2kbnlpp13kwvk192825y8pykhiag-ttyd-1.7.7/bin/ttyd --port 7681 --interfac
hacker 128 124 0 14:55 pts/0 00:00:00 /run/dojo/bin/bash --login
hacker 133 0 0 14:55 pts/1 00:00:00 /nix/store/pkf547jp8a92k4wmxikkyby58w10pysr-bash-interactive-5.3p9/bin/bash /run/dojo/
hacker 139 133 0 14:55 pts/1 00:00:00 /run/dojo/bin/bash --login
hacker 147 139 0 14:56 pts/1 00:00:00 ps -ef
hacker@processes~listing-processes:~$ /challenge/20924-run-19933
Yahaha, you found me! Here is your flag:
pwn.college{A_s0vJ1-tQuROAP-9AW4YLctkUE.QX4MDO0wyMwEzM2EzW}
Now I will sleep for a while (so that you could find me with 'ps').
ps aux
ps pwn.college{A_s0vJ1-tQuROAP-9AW4YLctkUE.QX4MDO0wyMwEzM2EzW}
^C
hacker@processes~listing-processes:~$ ps /challenge/20924-run-19933
error: garbage option

Usage:
ps [options]

Try 'ps --help <simple|list|output|threads|misc|all>'
or 'ps --help <s|l|o|t|m|a>'
for additional help text.

For more details see ps(1).
hacker@processes~listing-processes:~$ ps aux /challenge/20924-run-19933
error: garbage option

Usage:
ps [options]

Try 'ps --help <simple|list|output|threads|misc|all>'
or 'ps --help <s|l|o|t|m|a>'
for additional help text.

For more details see ps(1).
hacker@processes~listing-processes:~$
```

## Flag

```
pwn.college{A_s0vJ1-tQuROAP-9AW4YLctkUE.QX4MDO0wyMwEzM2EzW}
```
