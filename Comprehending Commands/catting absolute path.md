# Catting Absolute Path

> Module: **Comprehending Commands** · Challenge: `catting-absolute-paths`

`cat`-ыг absolute path-аар хэрэглэнэ — flag нь `/flag` (root доор) байгаа.

## Тайлбар

- `cat /flag` — `/` (root)-аас эхэлсэн **absolute path** ашиглаж байна.
- `cat /challenge/` — `/challenge/` нь директор, файл биш. `cat` директор уншиж чадахгүй.
- `cat /challenge/run` — challenge-ийн script. Дотроо ямар комманд ажиллуулдгийг харж болно — энэ нь `cat /challenge/DESCRIPTION.md` дуудаж байна.
- Шийдэл: `cat /flag` гэж шууд root доорх `flag` файлыг унш.

## Solution

```console
hacker@commands~catting-absolute-paths:~$ cat /challenge/run
#!/bin/bash

cat /challenge/DESCRIPTION.md
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{AFkSVRJJp3gvco-SX_AktrggD8u.QX5ETO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{AFkSVRJJp3gvco-SX_AktrggD8u.QX5ETO0wyMwEzM2EzW}
```
