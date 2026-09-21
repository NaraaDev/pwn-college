# Fun With Groups Names

> Module: **Linux Luminarium / Perceiving Permission** · Challenge: `fun-with-groups-names`

Санамсаргүй нэртэй болгосон өөрийн бүлгийг `id`-ээр олж, `chgrp`-ээр `/flag`-ийн бүлгийг сольж уншина.

## Тайлбар

- Хэрэглэгч бүр өөрийн нэртэй ижил нэртэй бүлэгтэй байх нь Linux-ийн **конвенц** (`hacker` → `hacker`, `zardus` → `zardus`), заавал биш. Компьютерийн лаб зэрэгт бүх хэрэглэгчийг нэг `users` бүлэгт оруулдаг.
- Энэ level-д `hacker`-ийн бүлгийн нэрийг санамсаргүй болгосон: `id` → `gid=1000(grp24855) groups=1000(grp24855)`. Нэр нь дахин эхлүүлэх бүрт өөр байна.
- `chgrp grp24855 /flag` → `/flag`-ийн бүлэг бидний бүлэг болж, `-r--r-----`-ийн бүлгийн `r` битээр `cat /flag` уншигдана.

## Solution

```console
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp24855) groups=1000(grp24855)
hacker@permissions~fun-with-groups-names:~$ /challenge/run
I have given you access to use the 'chgrp' command. Use it to enable the flag
to be read, but first use 'id' to figure out the group name!
hacker@permissions~fun-with-groups-names:~$ chgrp grp24855 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
pwn.college{sqe0a2KnjK99PpMn-g0cW8rel9K.QXycjM1wyMwEzM2EzW}
hacker@permissions~fun-with-groups-names:~$
```

## Flag

```
pwn.college{sqe0a2KnjK99PpMn-g0cW8rel9K.QXycjM1wyMwEzM2EzW}
```
