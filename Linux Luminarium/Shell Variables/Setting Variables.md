# Setting Variables

> Module: **Linux Luminarium / Shell Variables** · Challenge: `setting-variables`

`VAR=value` хэлбэрээр shell хувьсагчид утга онооно.

## Тайлбар

- `PWN="COLLEGE"` — `PWN` нэртэй хувьсагчид `COLLEGE` утгыг онооно. `=` тэмдгийн хоёр талд **зай байж болохгүй**: `PWN = COLLEGE` гэвэл shell нь `PWN`-ийг команд гэж ойлгоно.
- Хувьсагчийн нэр том/жижиг үсэг ялгаатай (case-sensitive) — `PWN` ба `pwn` нь өөр өөр хувьсагч.
- Оноохдоо `$`-гүй (`PWN=...`), уншихдаа `$`-тэй (`$PWN`) бичнэ.

## Solution

```console
hacker@variables~setting-variables:~$ PWN="COLLEGE"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{oXwLKLYmzsLq4OLUjAqXIE2stMv.QX5UTN0wyMwEzM2EzW}
```

## Flag

```
pwn.college{oXwLKLYmzsLq4OLUjAqXIE2stMv.QX5UTN0wyMwEzM2EzW}
```
