# The Flag File

> Module: **Start Here** · Challenge: `the-flag-file`

Бараг бүх challenge-д `flag` файл байх бөгөөд агуулга нь `pwn.college{...}` форматтай. Энэ файл хаана байх, хэрхэн уншихыг танилцуулна.

## Тайлбар

- **Flag** — challenge амжилттай бодсоны баталгаа. Pаrk format: `pwn.college{<random>}`.
- Ихэвчлэн `/flag` (root доор) эсвэл `/challenge/...` доор байрладаг.
- Уншихад `cat` комманд хэрэглэнэ: `cat /flag`.
- Заримдаа `/flag` зөвхөн root уншдаг (`mode 0400`) — тэр үед challenge-ийн privileged program `flag`-ыг гаргаж өгдөг.

```bash
cat /flag
```

## Flag

```
pwn.college{QtfzucUuUOnMtRBJdEf2g5Ub2WN.QX5IzNzwyMwEzM2EzW}
```
