# Executable Files

> Module: **Linux Luminarium / Perceiving Permission** · Challenge: `executable-files`

Execute битгүй `/challenge/run`-д `chmod +x`-ээр ажиллуулах эрх нэмж, флагийг хэвлүүлнэ.

## Тайлбар

- Програмыг ажиллуулахын тулд тухайн файлд **execute** (`x`) эрхтэй байх ёстой. `/challenge/run` нь `root:root` эзэмшилтэй бол `hacker`-т **other**-ийн `x` бит хэрэгтэй; `chmod o-x` хийвэл `bash: /challenge/run: Permission denied`.
- Энэ level-д `/challenge/run` нь `-rw-r--r-- 1 hacker hacker` — `x` бит огт байхгүй тул `Permission denied`. Файлын эзэн `hacker` учраас `chmod` хийж болно: `chmod +x /challenge/run` → ажиллаж флаг хэвлэнэ.
- `/flag`-д `chmod +w` / `chmod +r` хийхэд `Operation not permitted` — эзэн нь root тул энэ level-д `chmod` хүчгүй (өмнөх level-ийн all-powerful chmod энд байхгүй).
- `chmod +e` → `invalid mode` — execute-ийн тэмдэг `e` биш **`x`**. `chmod +w` нь бичих эрх нэмэх тул ажиллуулахад тус болоогүй, `o-x` нь байхгүй битийг хассан.
- `/challenge/r`, `//challenge/r` гэж дутуу бичихэд `No such file or directory` — Tab completion-оор бүтэн нэрийг бичих нь найдвартай.

## Solution

```console
hacker@permissions~executable-files:~$ ls -l /flag
-r-------- 1 root root 60 Sep 21 14:42 /flag
hacker@permissions~executable-files:~$ chmod +w /flag
chmod: changing permissions of '/flag': Operation not permitted
hacker@permissions~executable-files:~$ chmod +r /flag
chmod: changing permissions of '/flag': Operation not permitted
hacker@permissions~executable-files:~$ //challenge/r
bash: //challenge/r: No such file or directory
hacker@permissions~executable-files:~$ /challenge/r
bash: /challenge/r: No such file or directory
hacker@permissions~executable-files:~$ /challenge/run
bash: /challenge/run: Permission denied
hacker@permissions~executable-files:~$ chmod +w /challenge/run
hacker@permissions~executable-files:~$ /challenge/r
bash: /challenge/r: No such file or directory
hacker@permissions~executable-files:~$ /challenge/run
bash: /challenge/run: Permission denied
hacker@permissions~executable-files:~$ chmod +e /challenge/run
chmod: invalid mode: ‘+e’
Try 'chmod --help' for more information.
hacker@permissions~executable-files:~$ chmod o-x /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
bash: /challenge/run: Permission denied
hacker@permissions~executable-files:~$ ls -l /challenge/run
-rw-r--r-- 1 hacker hacker 32 Jul 24 06:05 /challenge/run
hacker@permissions~executable-files:~$ chmod +x /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
Successful execution! Here is your flag:
pwn.college{M5rr8XMzn-49p3TK0ZuGRDDUxYu.QXyEjN0wyMwEzM2EzW}
hacker@permissions~executable-files:~$
```

## Flag

```
pwn.college{M5rr8XMzn-49p3TK0ZuGRDDUxYu.QXyEjN0wyMwEzM2EzW}
```
