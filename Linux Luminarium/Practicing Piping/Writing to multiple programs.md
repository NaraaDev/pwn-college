# Writing To Multiple Programs

> Module: **Linux Luminarium / Practicing Piping** · Challenge: `writing-to-multiple-programs`

`tee` болон `>(...)` процесс орлуулалтыг хослуулан нэг гаралтыг зэрэг хоёр программын оролт руу хуулбарлана.

## Тайлбар

- `/challenge/hack | tee >(/challenge/the) >(/challenge/planet)` — `/challenge/hack`-ийн гаралтыг `tee`-ээр авч, `>(...)` процесс орлуулалт ашиглан **зэрэг** `/challenge/the` болон `/challenge/planet` хоёр программын stdin рүү дамжуулна.
- Өгөгдөл (`secret` тоо) хурдан өөрчлөгддөг тул завсарлаж, гараар хуулах боломжгүй — хоёр программ руу яг нэгэн зэрэг очих ёстой байсан.
- `tee` олон гаралтын target авах чадвартай тул нэг stream-ийг хэд ч хэдэн процесс руу зэрэг салгаж чаддаг.

## Solution

```console
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >(/challenge/the) >(/challenge/planet)
This secret data must directly and simultaneously make it to /challenge/the and
/challenge/planet. Don't try to copy-paste it; it changes too fast.
10843266622229911006
Congratulations, you have duplicated data into the input of two programs! Here
is your flag:
pwn.college{wfV5_VmRD8-MBNhogAB_crJ1Jjs.QXwgDN1wyMwEzM2EzW}
```

## Flag

```
pwn.college{wfV5_VmRD8-MBNhogAB_crJ1Jjs.QXwgDN1wyMwEzM2EzW}
```
