# Finding Commands

> Module: **Linux Luminarium / Pondering Path** · Challenge: `finding-commands`

`which win`-ээр `win` командын байршлыг олоод, тэр директорт байгаа `flag` файлыг `cat`-аар уншина.

## Тайлбар

- Командын нэрийг бичихэд (builtin биш бол) `$PATH`-д жагсаасан директоруудын аль нэг дэх файл ажилладаг. Яг аль файл болохыг `which` командаар олно: `which cat` → `/bin/cat`.
- `which` нь shell-тэй адил `$PATH`-ийн директоруудыг дарааллаар нь шалгаж, нэр таарсан **эхний** файлыг хэвлэнэ.
- Энд `win` өөрөө флаг өгөхгүй, харин түүнтэй нэг директорт уншигдах эрхтэй `flag` файл байгаа. `which win` → `/challenge/paths/29366/win`, tab completion нь тэр директорт `flag`, `win` хоёр байгааг харуулна → `cat /challenge/paths/29366/flag`.

## Solution

```console
hacker@path~finding-commands:~$ which win
/challenge/paths/29366/win
hacker@path~finding-commands:~$ cat /challenge/paths/29366/
flag win
hacker@path~finding-commands:~$ cat /challenge/paths/29366/flag
pwn.college{0n56KqmMPDz8QSdMKJZFtEB-U-n.01NzEzNxwyMwEzM2EzW}
hacker@path~finding-commands:~$
```

## Flag

```
pwn.college{0n56KqmMPDz8QSdMKJZFtEB-U-n.01NzEzNxwyMwEzM2EzW}
```
