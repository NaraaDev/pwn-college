# Redirecting Input

> Module: **Linux Luminarium / Practicing Piping** · Challenge: `redirecting-input`

`<` дахин чиглүүлэлт ашиглан файлын агуулгыг программын стандарт оролт (stdin) руу дамжуулна.

## Тайлбар

- `/challenge/run < PWN` — `PWN` файлын агуулгыг challenge программын stdin рүү дамжуулна.
- Эхлээд `PWN` файл байхгүй/хоосон байсан тул `echo COLLEGE > PWN`-ээр шаардлагатай агуулгыг үүсгэсэн.
- Дараа нь дахин ажиллуулахад программ `PWN`-ийн агуулга `COLLEGE` болохыг зөв уншиж, флагийг өгсөн.

## Solution

```console
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Your PWN file must have the value 'COLLEGE', but I instead read: You have not
redirected anything to my standard input. Please do so, using '<'.
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{4kn7dVP2X31dOL8vwFkAr2ZX54a.QXwcTN0wyMwEzM2EzW}
```

## Flag

```
pwn.college{4kn7dVP2X31dOL8vwFkAr2ZX54a.QXwcTN0wyMwEzM2EzW}
```
