# Interrupting Processes

> Module: **Linux Luminarium / Processess and Jobs** · Challenge: `interrupting-processes`

Терминалыг зуурсан процессыг `Ctrl-C`-ээр тасалж флаг авна.

## Тайлбар

- `Ctrl-C` нь терминалаас оролт хүлээж байгаа программд "interrupt" (SIGINT) илгээдэг терминалын hotkey — программ ихэвчлэн цэвэрхэн гарна.
- `kill`-ээс хялбар: PID хайх шаардлагагүй, терминалыг эзэлж байгаа процесст шууд нөлөөлнө.
- `/challenge/run` нь өөрөө таслагдах хүртэл флагийг өгөхгүй.

## Solution

```console
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember,
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{4VEy69Cu4mWE9FeaBpxO-ESRVol.QXzQDO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{4VEy69Cu4mWE9FeaBpxO-ESRVol.QXzQDO0wyMwEzM2EzW}
```
