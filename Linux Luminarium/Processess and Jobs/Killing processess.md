# Killing Processes

> Module: **Linux Luminarium / Processess and Jobs** · Challenge: `killing-processes`

`ps -ef`-ээр `/challenge/dont_run`-ийн PID-ийг олж, `kill`-ээр зогсоосны дараа `/challenge/run` флагийг өгнө.

## Тайлбар

- `kill` нь процессыг цэвэрхэн дуусгах боломж өгдөг (анхдагчаар SIGTERM илгээнэ) — процесс өөрийн ажлыг цэгцлээд гарна.
- `kill` нь **PID** (эсвэл job spec) хүлээж авдаг, файлын зам биш: `kill /challenge/dont_run` → `bash: kill: not a pid or valid job spec`.
- `ps -ef`-д `hacker 110 109 ... /challenge/dont_run` мөр байсан тул PID нь **110**.
- `kill 110` → процесс зогсож, `/challenge/run` флагийг гаргав.

## Solution

```console
hacker@processes~killing-processes:~$ /challenge/run
Nope! /challenge/dont_run is still running! You gotta terminate it before I
give you the flag!
hacker@processes~killing-processes:~$ kill /challenge/run
bash: kill: `/challenge/run': not a pid or valid job spec
hacker@processes~killing-processes:~$ /challenge/dont_run
d
^C
hacker@processes~killing-processes:~$ kill /challenge/dont_run
bash: kill: `/challenge/dont_run': not a pid or valid job spec
hacker@processes~killing-processes:~$ kill /challenge/run
bash: kill: `/challenge/run': not a pid or valid job spec
hacker@processes~killing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 14:58 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/
root           7       1  0 14:58 ?        00:00:00 /run/dojo/bin/sleep 6h
root         109       1  0 14:58 ?        00:00:00 su -c /challenge/.launcher hacker
hacker       110     109  0 14:58 ?        00:00:00 /challenge/dont_run
hacker       111     110  0 14:58 ?        00:00:00 sleep 6h
hacker       119       0  0 14:58 pts/0    00:00:00 /nix/store/pkf547jp8a92k4wmxikkyby58w10pysr-bash-interactive-5.3p9/bin/bash /run/dojo/
hacker       126     119  0 14:58 pts/0    00:00:00 /run/dojo/bin/bash --login
hacker       132       1  0 14:58 ?        00:00:00 /nix/store/nzhm2kbnlpp13kwvk192825y8pykhiag-ttyd-1.7.7/bin/ttyd --port 7681 --interfac
hacker       134     132  0 14:58 pts/1    00:00:00 /run/dojo/bin/bash --login
hacker       145     126  0 14:59 pts/0    00:00:00 ps -ef
hacker@processes~killing-processes:~$ kill /challenge/dont_run
bash: kill: `/challenge/dont_run': not a pid or valid job spec
hacker@processes~killing-processes:~$ kill 110
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{EV6V3Q6orRDYTWNWw5Lb4ngzKtT.QXyQDO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{EV6V3Q6orRDYTWNWw5Lb4ngzKtT.QXyQDO0wyMwEzM2EzW}
```
