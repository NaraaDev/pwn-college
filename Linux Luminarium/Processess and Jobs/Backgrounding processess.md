# Backgrounding Processes

> Module: **Linux Luminarium / Processess and Jobs** · Challenge: `backgrounding-processes`

`Ctrl-Z` → `bg`-ээр процессыг дэвсгэрт **ажиллаж байгаа** хэвээр сэргээж, дараа нь хоёр дахь хувийг ажиллуулж флаг авна.

## Тайлбар

- `fg` процессыг foreground-д сэргээдэг бол `bg` нь дэвсгэрт сэргээнэ — процесс ажиллаж байхад терминал чөлөөтэй хэвээр байна.
- Suspend ба background хоёр **өөр төлөв**. `ps -o user,pid,stat,cmd`-ийн `STAT` баганаар харна:

| STAT | Тайлбар |
|------|---------|
| `T` | `Ctrl-Z`-ээр түр зогссон (stopped). |
| `S` | Унтаж байгаа боловч зогсоогүй — `bg` хийсний дараах төлөв. |
| `R` | Тухайн үед гүйж байгаа. |
| `+` | Foreground-д байгаа (дэвсгэрийн процесст `+` байхгүй). |

- Энэ level-ийн `run` нь ижил терминал дээр өөрийн хуулбар **зогсоогүй** ажиллаж байхыг шаарддаг: эхний хувийг `Ctrl-Z` → `bg`-ээр дэвсгэрт ажиллуулсны дараа хоёр дахийг ажиллуулна. Гаралтын `root 176 S /bin/bash -p /challenge/run` мөр нь `+`-гүй `S` — яг дэвсгэрт ажиллаж байгаа хувь.

## Solution

```console
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running _and
not suspended_ in this terminal... Let's check!

UID PID STAT CMD
root 176 S /bin/bash -p /challenge/run
root 186 S sleep 6h
root 192 S+ /bin/bash -p /challenge/run
root 194 R+ ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{IQyWEgv6dOkvWkYB6S-s9HTX0EY.QX3QDO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{IQyWEgv6dOkvWkYB6S-s9HTX0EY.QX3QDO0wyMwEzM2EzW}
```
