# Deleting Characters

> Module: **Linux Luminarium / Data Manipulation** · Challenge: `deleting-characters`

`tr -d` тугаар гаралтад холилдсон хогийн тэмдэгтүүдийг устгаж, цэвэр флагийг гаргана.

## Тайлбар

- `/challenge/run` нь флагийг `^` ба `%` тэмдэгтүүдээр дүүргэж (character-stuffed) хэвлэдэг.
- `tr -d ^%` — `-d` (delete) тугтай үед `tr` нь орлуулалт хийхгүй, зөвхөн заасан олонлогт орсон **бүх** тэмдэгтийг гаралтаас хасна.
- `^` ба `%` нь bash-д тусгай утгагүй тул хашилтгүй бичсэн ч ажиллана, гэхдээ `tr -d '^%'` гэж хашилтанд авах нь найдвартай.

## Solution

```console
hacker@data~deleting-characters:~$ /challenge/run | tr -d ^%
Your character-stuffed flag:
pwn.college{c8k-_2wlASRUBrBo_9BBsUFdYT-.0FNxEzNxwyMwEzM2EzW}
```

## Flag

```
pwn.college{c8k-_2wlASRUBrBo_9BBsUFdYT-.0FNxEzNxwyMwEzM2EzW}
```
