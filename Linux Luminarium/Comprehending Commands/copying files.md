# Copying Files

> Module: **Comprehending Commands** · Challenge: `copying-files`

`cp` — файлын **хуулбар** үүсгэх. `mv` шиг ажилладаг ч анхны файлыг үлдээдэг.

## Тайлбар

- `cp <src> <dst>` — `<src>` файлыг `<dst>` руу хуулна.
- `cp -r <dir> <dst>` — директорыг бүхэлд нь хуулна (recursive).
- `cp file.txt /tmp/` — `/tmp/file.txt` нэртэйгээр хуулна.
- Challenge: `/flag`-ийг `/tmp/hack-the-planet` рүү хуулна.

```bash
cp /flag /tmp/hack-the-planet
cp -r dir1/ dir2/
```

## `cp` vs `mv`

| Комманд | Эх файл | Зорилго файл |
|---------|---------|-------------|
| `cp` | Үлдэнэ | Шинээр үүснэ |
| `mv` | Алга болно | Шинэ байрлалд үүснэ |

## Solution

```console
hacker@commands~copying-files:~$ cp /flag /tmp/hack-the-planet
Correct! Performing 'cp /flag /tmp/hack-the-planet'.
hacker@commands~copying-files:~$ /challenge/check
Congrats! You successfully copied the flag to /tmp/hack-the-planet! Here it is:
pwn.college{cXi2fgVZUetAy1jUbUwuCU4Omlt.0lNxQTMywyMwEzM2EzW}
```

## Flag

```
pwn.college{cXi2fgVZUetAy1jUbUwuCU4Omlt.0lNxQTMywyMwEzM2EzW}
```
