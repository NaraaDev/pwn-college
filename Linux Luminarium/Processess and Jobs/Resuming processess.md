# Resuming Processes

> Module: **Linux Luminarium / Processess and Jobs** · Challenge: `resuming-processes`

`Ctrl-Z`-ээр зогсоосон процессыг shell-ийн `fg` builtin-ээр сэргээж foreground-д буцаана.

## Тайлбар

- `fg` (foreground) нь зогссон процессыг сэргээж терминалын foreground-д буцаана — зогсоосон процессыг устгахгүй, дуусгахгүйгээр ажлаа үргэлжлүүлэх арга.
- Зогссон хэдий ч процесс жагсаалтад хэвээр байна: `ps -ef`-д `root 131 118 ... /bin/bash -p /challenge/run` мөр харагдсан.
- `fg` хийхэд shell тэр командын нэрийг эхлээд хэвлээд (`/challenge/run`), процесс ажлаа үргэлжлүүлж флагийг гаргав.

## Solution

```console
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+ Stopped /challenge/run
hacker@processes~resuming-processes:~$ ps -ef
UID PID PPID C STIME TTY TIME CMD
root 1 0 0 15:05 ? 00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/
root 7 1 0 15:05 ? 00:00:00 /run/dojo/bin/sleep 6h
hacker 104 0 0 15:05 pts/0 00:00:00 /nix/store/pkf547jp8a92k4wmxikkyby58w10pysr-bash-interactive-5.3p9/bin/bash /run/dojo/
hacker 118 104 0 15:05 pts/0 00:00:00 /run/dojo/bin/bash --login
hacker 123 1 0 15:05 ? 00:00:00 /nix/store/nzhm2kbnlpp13kwvk192825y8pykhiag-ttyd-1.7.7/bin/ttyd --port 7681 --interfac
hacker 125 123 0 15:05 pts/1 00:00:00 /run/dojo/bin/bash --login
root 131 118 0 15:07 pts/0 00:00:00 /bin/bash -p /challenge/run
hacker 133 118 0 15:07 pts/0 00:00:00 ps -ef
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{wt9H83Liqmcs8YLazp6HzNqqAGK.QX2QDO0wyMwEzM2EzW}
Don't forget to press Enter to quit me!

Goodbye!
hacker@processes~resuming-processes:~$
```

## Flag

```
pwn.college{wt9H83Liqmcs8YLazp6HzNqqAGK.QX2QDO0wyMwEzM2EzW}
```
