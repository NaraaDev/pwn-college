# Detaching and Attaching (tmux)

> Module: **Linux Luminarium / Terminal Multiplexing** · Challenge: `detaching-and-attaching-tmux`

`tmux`-ийг эхлүүлээд `Ctrl-B d`-ээр detach хийж, `/challenge/run`-ийг ажиллуулаад `tmux attach`-аар буцаж ороход флаг хүлээж байна.

## Тайлбар

- `tmux` (terminal multiplexer) нь screen-ийн илүү орчин үеийн хувилбар — ижил боломжтой ч prefix нь `Ctrl-A` биш **`Ctrl-B`**.
- Detach: `Ctrl-B`, дараа нь `d` → `[detached (from session 0)]`.
- `tmux ls` — session-уудыг жагсаах; `tmux attach` / `tmux a` — буцаж attach хийх.
- screen-ийн адил `/challenge/run` нь detach хийсэн session руу флагтай `echo` командыг илгээнэ.
- Дараалал: `tmux` → `Ctrl-B d` → `/challenge/run` → `tmux a`.
- Хуулсан хэсэгт зөвхөн session руу илгээгдсэн `echo` командын мөр үлдсэн — флаг командын аргументад байна.

## Solution

```console
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ echo Congratulations, here is your flag: pwn.college{sbc_tuQp96kUquPEIyQ0hbuzOvM.0VO4IDOxwyMwEzM2EzW}
```

## Flag

```
pwn.college{sbc_tuQp96kUquPEIyQ0hbuzOvM.0VO4IDOxwyMwEzM2EzW}
```
