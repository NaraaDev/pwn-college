# Using sudo

> Module: **Linux Luminarium / Untangling Users** · Challenge: `using-sudo`

`sudo`-гээр командыг root эрхээр ажиллуулж (`/challenge/run`), дараа нь `sudo cat /flag`-ээр флаг унших.

## Тайлбар

- `su` нь нууц үгээр баталгаажуулж shell нээдэг бол `sudo` нь **бодлого** (`/etc/sudoers`) шалгаж, командыг анхдагчаар **root болгож** ажиллуулна.
- `sudo whoami` → `root`; `sudo grep hacker /etc/shadow` нь эрхгүй уншиж чадахгүй файлыг уншина.
- Орчин үеийн администрац `su`-гээс `sudo`-руу шилжсэн — root password шаардлагагүй, fleet-д тохиромжтой. pwn.college-ийн Privileged Mode ч `sudo` эрхээр ажилладаг.
- Энд бидэнд `sudo` эрх өгсөн тул `sudo /challenge/run` → `sudo cat /flag`.

## Solution

```console
hacker@users~using-sudo:~$ sudo /challenge/run
Congratulations, you have run this command as root!
You can now read the flag yourself. Run: sudo cat /flag
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{8Tbq2KZA1PV3J-cJX-h22AGhtG6.QX4UDN1wyMwEzM2EzW}
hacker@users~using-sudo:~$
```

## Flag

```
pwn.college{8Tbq2KZA1PV3J-cJX-h22AGhtG6.QX4UDN1wyMwEzM2EzW}
```
