# The SUID Bit

> Module: **Linux Luminarium / Perceiving Permission** · Challenge: `the-suid-bit`

`/challenge/getroot`-д `chmod u+s`-ээр SUID бит тавьж, root shell нээгээд `/flag`-ийг уншина.

## Тайлбар

- **SUID** (Set User ID) бит — програмыг хэн ажиллуулснаас үл хамааран **файлын эзний** эрхээр ажиллуулна. `ls -l /usr/bin/sudo` → `-rwsr-xr-x 1 root root`: эзний `x` байрлалд `s` байвал SUID тавигдсан, эзэн нь `root` тул root эрхээр ажиллана.
- Энэ механизмаар `su`, `sudo` зэрэг администрацийн хэрэгслүүд, мөн pwn.college-ийн challenge програмууд `/flag`-ийг уншиж чаддаг — админ хэрэглэгч бүрд нууц үг өгөх шаардлагагүй.
- Файлын эзэн `chmod u+s [program]`-оор SUID бит тавина. Root эзэмшилтэй executable-д SUID өгөх нь халдагчид root болох зам нээж болзошгүй — Program Misuse модульд дэлгэрүүлнэ.
- Энэ level-д `/challenge/getroot`-д SUID бит тавихыг зөвшөөрсөн: `chmod u+s /challenge/getroot` → ажиллуулахад root shell (`root@...#` prompt) нээгдэж, `cat /flag` шууд уншигдана.

## Solution

```console
hacker@permissions~the-suid-bit:~$ chmod u+s /challenge/getroot
hacker@permissions~the-suid-bit:~$ /challenge/getroot
SUCCESS! You have set the suid bit on this program, and it is running as root!
Here is your shell...
root@permissions~the-suid-bit:/home/hacker# cat /flag
pwn.college{0SvU7xiVtLDhVlaEA7S-Q8P3UBP.QXzEjN0wyMwEzM2EzW}
root@permissions~the-suid-bit:/home/hacker#
```

## Flag

```
pwn.college{0SvU7xiVtLDhVlaEA7S-Q8P3UBP.QXzEjN0wyMwEzM2EzW}
```
