# Printing Exported Variables

> Module: **Linux Luminarium / Shell Variables** · Challenge: `printing-exported-variables`

`env` команд export хийгдсэн хувьсагчуудыг жагсаадаг; флаг нь export хийгдсэн `FLAG` хувьсагчид байна.

## Тайлбар

- `env` — export хийгдсэн, өөрөөр хэлбэл дэд процесс руу дамждаг хувьсагчуудыг бүгдийг хэвлэнэ. `FLAG` export хийгдсэн тул `env` эсвэл `env | grep FLAG` гэхэд шууд харагдана.
- Энд `env echo $FLAG` гэж ажиллуулсан. Shell нь `$FLAG`-ийг эхлээд утгаар нь сольсон тул `env` нь үнэндээ `echo <флаг>` командыг ажиллуулсан. Үр дүн нь `echo $FLAG`-тай яг адил, `env` энд бодит үүрэг гүйцэтгээгүй.
- Ердийн `VAR=value` оноолт зөвхөн одоогийн shell-д л үлддэг; `export VAR` хийсэн хувьсагч л дэд процесс (`env`, `/challenge/run` г.м.) руу дамжина.

## Solution

```console
hacker@variables~printing-exported-variables:~$ env echo $FLAG
pwn.college{cOaZdECAJRkW5J4jUC6BrtJ8Tri.QX4UTN0wyMwEzM2EzW}
```

## Flag

```
pwn.college{cOaZdECAJRkW5J4jUC6BrtJ8Tri.QX4UTN0wyMwEzM2EzW}
```
