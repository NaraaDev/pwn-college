# Starting Backgrounded Processes

> Module: **Linux Luminarium / Processess and Jobs** · Challenge: `starting-backgrounded-processes`

Командын төгсгөлд `&` тавьж процессыг эхнээсээ дэвсгэрт ажиллуулна.

## Тайлбар

- `command &` — shell тэр командыг шууд дэвсгэрт ажиллуулж, `[1] 168` гэж **job дугаар** ба **PID**-ийг хэвлэнэ. `Ctrl-Z` + `bg` хийх шаардлагагүй.
- Ингэж ажиллуулсан процесс зогссон биш, ажиллаж байна: `ps -o user,pid,stat,cmd`-д `STAT` нь `S` (foreground-ийн `+` тэмдэггүй).
- Гаралт нь дэвсгэрээс хэвлэгддэг тул prompt-той хольж харагдана.

## Solution

```console
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 168
hacker@processes~starting-backgrounded-processes:~$

Yay, you started me in the background! Because of that, this text will probably
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{oP2hOSfSNREAkJxzBh4Dfn77_jQ.QX5QDO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{oP2hOSfSNREAkJxzBh4Dfn77_jQ.QX5QDO0wyMwEzM2EzW}
```
