# Groups and Files

> Module: **Linux Luminarium / Perceiving Permission** · Challenge: `groups-and-files`

`/flag`-ийн эзэн бүлгийг `chgrp`-ээр `hacker` болгож, бүлгийн унших эрхээр флагийг уншина.

## Тайлбар

- Файл эзэн хэрэглэгчээс гадна **эзэн бүлэгтэй**. Бүлэгт олон хэрэглэгч, хэрэглэгч олон бүлэгт байж болно. `id` командаар `uid`, `gid` (үндсэн бүлэг), `groups` (бүх бүлэг)-ээ харна: `uid=1000(hacker) gid=1000(hacker) groups=1000(hacker)`.
- Бүлэг нь системийн нөөцөд хандах эрхийг удирдах хамгийн түгээмэл арга: pwn.college-ийн Privileged Mode `27(sudo)` бүлэг нэмж өгдөг; desktop дээр `video` бүлэг `/dev/fb0` (`c` — character device) руу бичих эрх өгдөг гэх мэт.
- `chgrp [group] [file]` — файлын эзэн бүлгийг солино. Ердийн үед root, эсвэл файлын эзэн бөгөөд шинэ бүлгийн гишүүн байх шаардлагатай; энэ level-д `hacker`-т `chgrp`-ийг шууд ажиллуулах эрх өгсөн.
- Энэ level-д `/flag` нь `-r--r-----` — бүлэг унших эрхтэй боловч бүлэг нь `root`. `chgrp hacker /flag` → бүлэг `hacker` болж, `hacker` тэр бүлгийн гишүүн тул `cat /flag` уншигдана.

## Solution

```console
hacker@permissions~groups-and-files:~$ id
uid=1000(hacker) gid=1000(hacker) groups=1000(hacker)
hacker@permissions~groups-and-files:~$ /challenge/run
I have given you access to use the 'chgrp' command. Use it to enable the flag
to be read!
hacker@permissions~groups-and-files:~$ chgrp hacker /flag
hacker@permissions~groups-and-files:~$ cat /flag
pwn.college{4Fta7SazZjIldZgJ06eggE5e5ou.QXxcjM1wyMwEzM2EzW}
hacker@permissions~groups-and-files:~$
```

## Flag

```
pwn.college{4Fta7SazZjIldZgJ06eggE5e5ou.QXxcjM1wyMwEzM2EzW}
```
