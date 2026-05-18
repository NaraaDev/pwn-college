# Matching Paths with []

> Module: **Linux Luminarium / File Globbing** · Challenge: `matching-paths-with-`

`[]` glob-оор бүтэн зам (path) тааруулах. Энэ удаа аргументийг challenge-ийн программд яг файлуудыг өргөтгөж дамжуулна.

## Тайлбар

- `[abhs]` — `a`, `b`, `h`, `s` тэмдэгтүүдийн аль нэг тэмдэгт.
- `file_[abhs]` — `file_a`, `file_b`, `file_h`, `file_s` файлуудыг бүгдийг тааруулна.
- `\_` — backslash-аар escape хийсэн `_`. Утгын хувьд жирийн `_`-тэй адил, заавал шаардлагагүй ч ашиглаж болно.

```bash
/challenge/run /challenge/files/file_[abhs]
```

## Solution

```console
hacker@globbing~matching-paths-with-:~$ /challenge/run
Error: you did not use a square bracket glob...
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file\_[abhs]
```

## Flag

> Бодоогүй / тэмдэглэлгүй.
