# Learning from Documentation

> Module: **Linux Luminarium / Digesting Documentation** · Challenge: `learning-from-documentation`

Challenge description-ийг уншиж, зааврын дагуу зөв аргумент дамжуулах сорилт. `/challenge/challenge --giveflag` гэж ажиллуулахад flag өгнө.

## Тайлбар

| Команд | Тайлбар |
|--------|---------|
| `/challenge/challenge` | Аргументгүй ажиллуулахад алдааны мэдэгдэл гаргана. |
| `/challenge/challenge --giveflag` | Зохиомлоор тодорхойлсон `--giveflag` аргументыг дамжуулахад flag өгнө. |

Challenge нь documentation уншиж, заасан аргументыг олж хэрэглэх чадварыг шалгана. `--giveflag` аргументыг challenge-ийн тайлбараас олсон.

## Solution

```console
hacker@man~learning-from-documentation:~$ /challenge/challenge
Incorrect usage! You must pass an argument to me (read the challenge
description for details).

hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{Ad5xdN1Z4tS0g0BVLs6cwebNRyp.QX0ITO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{Ad5xdN1Z4tS0g0BVLs6cwebNRyp.QX0ITO0wyMwEzM2EzW}
```
