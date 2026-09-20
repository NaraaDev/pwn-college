# Foregrounding Processes

> Module: **Linux Luminarium / Processess and Jobs** · Challenge: `foregrounding-processes`

Процессыг `Ctrl-Z`-ээр зогсоож, `bg`-ээр дэвсгэрт сэргээж, дараа нь `fg`-ээр foreground-д буцаана.

## Тайлбар

- `fg` нь зөвхөн зогссон процессыг биш, `bg`-ээр дэвсгэрт **ажиллаж байгаа** процессыг ч foreground-д авчирна.
- Job байхгүй үед `fg`/`bg` → `bash: fg: current: no such job`.
- Дараалал: `/challenge/run` → `Ctrl-Z` (`[1]+ Stopped`) → `bg` (`[1]+ /challenge/run &`) → `fg` → Enter → флаг.
- Дэвсгэрт ажиллаж байгаа процессын гаралт prompt-той хольж хэвлэгддэг — Enter дарж доош шахаж болно.

## Solution

```console
hacker@processes~foregrounding-processes:~$ fg
bash: fg: current: no such job
hacker@processes~foregrounding-processes:~$ fg
bash: fg: current: no such job
hacker@processes~foregrounding-processes:~$ bg
bash: bg: current: no such job
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the
background, and _then_ foreground it without re-suspending it! You can
background me with Ctrl-Z (and resume me in the background with 'bg') or, if
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+ Stopped /challenge/run
hacker@processes~foregrounding-processes:~$ bg
[1]+ /challenge/run &

Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out. After that, resume me into the foreground with 'fg';
I'll wait.
hacker@processes~foregrounding-processes:~$ fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{YH5Lx6Hh5wsrecFsUoYsnSeJAqJ.QX4QDO0wyMwEzM2EzW}
hacker@processes~foregrounding-processes:~$
```

## Flag

```
pwn.college{YH5Lx6Hh5wsrecFsUoYsnSeJAqJ.QX4QDO0wyMwEzM2EzW}
```
