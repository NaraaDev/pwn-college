# Changing Permissions

> Module: **Linux Luminarium / Perceiving Permission** · Challenge: `changing-permissions`

`chmod +r`-ээр `/flag`-д унших эрх нэмж (энэ level-д chmod бүхнийг чадна), флагийг уншина.

## Тайлбар

- `ls -l`-ийн эхний тэмдэгт файлын төрөл (`-` файл, `d` директор, `l` symlink, `c` character device), дараагийн 9 тэмдэгт нь 3×3 эрх: **user** (эзэн), **group** (эзэн бүлэг), **other** (бусад бүгд). Жишээ нь `rw-r--r--` → эзэн унших/бичих, бүлэг унших, бусад унших.

| Бит | Файлд | Директорт |
|-----|-------|-----------|
| `r` | уншина | жагсаана (`ls`) |
| `w` | өөрчилнө | дотор нь файл үүсгэх/устгах |
| `x` | програм болгож ажиллуулна | дотор нь орно (`cd`) |
| `-` | эрх байхгүй | эрх байхгүй |

- `chmod [OPTIONS] MODE FILE` — `MODE`-ийг `WHO+/-WHAT` хэлбэрээр өгвөл одоо байгаа эрхийг **өөрчилнө**: `u+r` (эзэнд унших нэмэх), `g+wx`, `o-w`, `a-rwx` (бүгдээс бүх эрх хасах). `WHO`-г орхивол (`+r`) `a` (бүгд) гэж ойлгоно.
- Анхдагч `/flag` нь `-r--------` — зөвхөн эзэн `root` уншина. Өмнөх chgrp level-үүдэд зориуд `-r--r-----` (бүлэг унших эрхтэй) болгосон байсан тул chgrp ажилласан.
- Ердийн үед файлын эзэн л `chmod` хийж чаддаг; энэ level-д `chmod`-ыг all-powerful болгосон тул `hacker` ч `/flag`-ийн эрхийг сольж чадна (эзнийг нь сольж чадахгүй ч). `chmod +r /flag` → `cat /flag` уншигдана.
- Home дахь `flag` (`-rw-r--r-- hacker hacker`, 0 байт) нь өмнөх level-ийн үлдэгдэл хоосон файл — `/flag`-тай андуурахгүй.

## Solution

```console
hacker@permissions~changing-permissions:~$ ls -l flag
-rw-r--r-- 1 hacker hacker 0 Jul 22 08:46 flag
hacker@permissions~changing-permissions:~$ ls -l /flag
-r-------- 1 root root 60 Sep 21 14:39 /flag
hacker@permissions~changing-permissions:~$ chmod +r /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{AY0uiV67OsYW7-aH3-RGwyA9Vm-.QXzcjM1wyMwEzM2EzW}
hacker@permissions~changing-permissions:~$
```

## Flag

```
pwn.college{AY0uiV67OsYW7-aH3-RGwyA9Vm-.QXzcjM1wyMwEzM2EzW}
```
