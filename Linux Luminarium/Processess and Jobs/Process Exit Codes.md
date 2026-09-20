# Process Exit Codes

> Module: **Linux Luminarium / Processess and Jobs** · Challenge: `process-exit-codes`

`/challenge/get-code`-ийн exit code-ыг `$?`-ээр уншиж, тэр кодыг `/challenge/submit-code`-д аргумент болгон дамжуулна.

## Тайлбар

- Процесс бүр дуусахдаа exit code буцаадаг: `0` — амжилттай, `0`-ээс өөр (ихэвчлэн `1`, эсвэл тодорхой алдааны код) — бүтэлгүй.
- Хамгийн сүүлд дууссан командын exit code нь тусгай `?` хувьсагчид хадгалагдана — уншихдаа `$?` гэж бичнэ.
- `$?`-г **дараагийн ямар ч команд дарж бичдэг**. `/challenge/get-code` → `ps -ef` → `echo $?` бол `ps`-ийн код гарна. Тиймээс эхний оролдлого (`16`) буруу байсан — хооронд өөр командууд ажилласан.
- `$?`-г бие даан команд болгож бичих нь тэр **тоог** ажиллуулах гэсэн үг: `bash: 179: command not found`.
- Exit code нь ажиллуулах болгонд өөр байдаг (16, 179, 185…) тул `get-code`-ийн **дараа шууд** `echo $?` хийж, гарсан кодыг `submit-code`-д дамжуулна: `185` → `CORRECT!`.

## Solution

```console
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ ps -ef
UID PID PPID C STIME TTY TIME CMD
root 1 0 0 15:24 ? 00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/
root 7 1 0 15:24 ? 00:00:00 /run/dojo/bin/sleep 6h
hacker 111 0 0 15:24 pts/0 00:00:00 /nix/store/pkf547jp8a92k4wmxikkyby58w10pysr-bash-interactive-5.3p9/bin/bash /run/dojo/
hacker 119 1 0 15:24 ? 00:00:00 /nix/store/nzhm2kbnlpp13kwvk192825y8pykhiag-ttyd-1.7.7/bin/ttyd --port 7681 --interfac
hacker 120 111 0 15:24 pts/0 00:00:00 /run/dojo/bin/bash --login
hacker 125 119 0 15:24 pts/1 00:00:00 /run/dojo/bin/bash --login
hacker 132 120 0 15:25 pts/0 00:00:00 ps -ef
hacker@processes~process-exit-codes:~$ /challenge/r
bash: /challenge/r: No such file or directory
hacker@processes~process-exit-codes:~$ /challenge/get-ode
bash: /challenge/get-ode: No such file or directory
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
16
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ /challenge/submit-code
You must run /challenge/submit-code with the exit code you retrieved from
/challenge/get-code as the first argument:

Usage: /challenge/submit-code [EXIT_CODE]
hacker@processes~process-exit-codes:~$ /challenge/submit-code 16
Incorrect... Make sure to use $? immediately after running /challenge/get-code.
Your shell will overwrite the $? variable with the exit value of any other
command you run!
hacker@processes~process-exit-codes:~$ $?
bash: 1: command not found
hacker@processes~process-exit-codes:~$ $? /challenge/get-code
bash: 127: command not found
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ $?
bash: 179: command not found
hacker@processes~process-exit-codes:~$ /challenge/get-code $?
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
185
hacker@processes~process-exit-codes:~$ /challenge/submit-code 185
CORRECT! Here is your flag:
pwn.college{s7GGOb495sW9vejNog_RSW1W1Kp.QX5YDO1wyMwEzM2EzW}
hacker@processes~process-exit-codes:~$
```

## Flag

```
pwn.college{s7GGOb495sW9vejNog_RSW1W1Kp.QX5YDO1wyMwEzM2EzW}
```
