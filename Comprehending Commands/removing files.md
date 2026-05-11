# Removing Files

> Module: **Comprehending Commands** · Challenge: `removing-files`

`rm` — файлыг устгах. Анхааруулга: устгасан файл `Trash` руу очдоггүй, шууд алга болно.

## Тайлбар

- `rm <file>` — заасан файлыг устгана.
- `rm -r <dir>` — директор болон дотроос нь устгах (recursive).
- `rm -f <file>` — баталгаажуулалт асуухгүй (force).
- ⚠️ `rm -rf /` гэх мэтийг **бүү** ажиллуул — систем бүхлээрээ устгана.
- Энэ challenge: home доор `delete_me` файл байна. Үүнийг устгасны дараа `/challenge/check`-г дуудна.

## Solution

```console
hacker@commands~removing-files:~$ ls
Desktop a delete_me leap rsa rsa.pub
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ ls
Desktop a leap rsa rsa.pub
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{4B9fBWxGAjgChGae1Y3JPquJJfc.QX2kDM1wyMwEzM2EzW}
```

## Flag

```
pwn.college{4B9fBWxGAjgChGae1Y3JPquJJfc.QX2kDM1wyMwEzM2EzW}
```
