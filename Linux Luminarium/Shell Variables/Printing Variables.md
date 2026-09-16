# Printing Variables

> Module: **Linux Luminarium / Shell Variables** · Challenge: `printing-variables`

Shell-ийн хувьсагчид хадгалагдсан утгыг `$` тэмдгээр авч `echo`-оор хэвлэнэ.

## Тайлбар

- `/challenge/run` — энэ удаад программ флаг өгөхгүй, харин флаг нь shell-ийн `FLAG` хувьсагчид аль хэдийн хадгалагдсан гэж хэлнэ.
- `echo $FLAG` — `$FLAG` гэж бичихэд shell нь командыг ажиллуулахаас **өмнө** хувьсагчийн утгаар нь сольдог (variable expansion). Тиймээс `echo` нь флагийг хэвлэнэ.
- `ls` — зүгээр л home директорыг харсан, шийдэлд шаардлагагүй алхам.

## Solution

```console
hacker@variables~printing-variables:~$ /challenge/run
You cannot solve this challenge using /challenge/run.
However, the flag is already in the FLAG variable in your shell.
Print it out!
hacker@variables~printing-variables:~$ ls
COLLEGE PWN asdf errors flag instractions leap not-the-flag rsa the-flag
Desktop a asf errors.log flag.md instructions myflag output.txt rsa.pub
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{AWXK4IsHR2BNMsKMBHcn7oa18pk.QX3UTN0wyMwEzM2EzW}
```

## Flag

```
pwn.college{AWXK4IsHR2BNMsKMBHcn7oa18pk.QX3UTN0wyMwEzM2EzW}
```
