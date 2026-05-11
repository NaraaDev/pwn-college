# Implicit Relative Paths, from /

> Module: **Linux Luminarium / Pondering Paths** · Challenge: `implicit-relative-paths-from-/`

`/` директорт байрлан `challenge/run` гэж implicit relative path-аар дуудна (`./` тэмдэглэгээгүй).

## Тайлбар

- `cd /` — root руу шилжих.
- `challenge/run` — `/` агаас эхэлсэн зам биш ч bash энэ хэлбэрийг **одоогийн директораас** эхэлсэн гэж тооцно. Тэр нь `/` тул `/challenge/run` =тай тэнцүү.
- `Is a directory` алдаа: `/tmp/` гэж заавар, дотор нь execute хийх program биш.

## Solution

```console
hacker@paths~implicit-relative-paths-from-:/tmp$ cd ..
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{Ech_6OV2VXqP0UY1vAmvzGIBrYe.QX5QTN0wyMwEzM2EzW}
```

## Flag

```
pwn.college{Ech_6OV2VXqP0UY1vAmvzGIBrYe.QX5QTN0wyMwEzM2EzW}
```
