# Moving Files

> Module: **Comprehending Commands** · Challenge: `moving-files`

`mv` — файлыг **зөөх** эсвэл **нэрийг өөрчлөх** (адил коммандаар хийгддэг).

## Тайлбар

- `mv <src> <dst>` —
  - `<dst>` шинэ нэр бол: файл шинэ нэртэйгээр **rename**.
  - `<dst>` байгаа директор бол: файлыг тэр директор руу **зөөнө**.
- Challenge: `/flag` файлыг `/tmp/hack-the-planet` болгож зөөнө.
- `cd /flag` ажиллахгүй — `/flag` нь файл, директор биш.

```bash
mv old.txt new.txt          # rename
mv file.txt /tmp/           # /tmp/file.txt руу зөөх
```

## Solution

```console
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{gWtezrpFvUn2Zm9PGEC-mYcFJp_.0VOxEzNxwyMwEzM2EzW}
```

## Flag

```
pwn.college{gWtezrpFvUn2Zm9PGEC-mYcFJp_.0VOxEzNxwyMwEzM2EzW}
```
