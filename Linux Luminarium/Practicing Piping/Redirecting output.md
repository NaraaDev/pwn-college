# Redirecting Output

> Module: **Linux Luminarium / Practicing Piping** · Challenge: `redirecting-output`

`>` дахин чиглүүлэлт ашиглан командын гаралтыг файлд бичнэ.

## Тайлбар

- `echo PWN > COLLEGE` — `echo` командын стандарт гаралт (`PWN`) дэлгэц рүү бус, `COLLEGE` нэртэй файл руу бичигдэнэ.
- `>` нь заасан файлыг байхгүй бол шинээр үүсгэж, байвал дарж бичнэ (overwrite).

## Solution

```console
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your
flag:
pwn.college{Qes-bY2ZWUZr4xOVc9Iutcjknmz.QX0YTN0wyMwEzM2EzW}
```

## Flag

```
pwn.college{Qes-bY2ZWUZr4xOVc9Iutcjknmz.QX0YTN0wyMwEzM2EzW}
```
