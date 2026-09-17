# Sorting Data

> Module: **Linux Luminarium / Data Manipulation** · Challenge: `sorting-data`

`sort`-оор файлын мөрүүдийг эрэмбэлж, олон хуурамч мөрийн дундаас хэрэгтэй өгөгдлөө олно.

## Тайлбар

- `sort /challenge/flags.txt` — файлын мөрүүдийг үсгийн дарааллаар (lexicographic) эрэмбэлж хэвлэнэ.
- `tr`, `cut`-аас ялгаатай нь `sort` нь файлын нэрийг **шууд аргумент** болгож авдаг тул заавал пайп хэрэггүй; мэдээж `... | sort` гэж пайпаар ч өгч болно.
- Ашигтай тугууд: `-n` (тооны дарааллаар), `-r` (урвуу), `-u` (давхардлыг хасах), `-k N` (N дахь талбараар эрэмбэлэх).

## Solution

```console
hacker@data~sorting-data:~$ sort /challenge/flags.txt
```

## Flag

> ⚠️ Энэ challenge-ийн гаралт бүртгэгдээгүй — флаг дутуу байна.
