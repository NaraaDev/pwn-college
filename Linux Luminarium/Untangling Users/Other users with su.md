# Other users with su

> Module: **Linux Luminarium / Untangling Users** · Challenge: `other-users-with-su`

`su`-д хэрэглэгчийн нэрийг аргумент болгож өгснөөр root биш, тухайн хэрэглэгч рүү шилжинэ.

## Тайлбар

- Аргументгүй `su` нь root shell нээдэг бол `su <username>` нь заасан хэрэглэгч рүү шилжинэ (тухайн хэрэглэгчийн нууц үгийг асууна).
- Энд `zardus` хэрэглэгч рүү шилжинэ — нууц үг нь `dont-hack-me`. Дараа нь `/challenge/run` флагийг өгнө.
- Prompt-ийн эхэнд байгаа хэрэглэгчийн нэр (`zardus@...`) шилжилт амжилттай болсныг харуулна.

## Solution

```console
hacker@users~other-users-with-su:~$ su zardus
Password:
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{YJvsnxt1PRROGtjFkj6qcCnjK1S.QX2UDN1wyMwEzM2EzW}
zardus@users~other-users-with-su:/home/hacker$
```

## Flag

```
pwn.college{YJvsnxt1PRROGtjFkj6qcCnjK1S.QX2UDN1wyMwEzM2EzW}
```
