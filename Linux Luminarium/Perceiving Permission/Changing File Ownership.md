# Changing File Ownership

> Module: **Linux Luminarium / Perceiving Permission** · Challenge: `changing-file-ownership`

`/flag`-ийн эзэмшигчийг `chown`-оор `hacker` болгож сольсноор root-ийн файлыг өөрөө уншина.

## Тайлбар

- Linux дээр файл бүр нэг **эзэн хэрэглэгч** (owner) болон нэг **эзэн бүлэгтэй** (group). `ls -l`-ийн 3, 4-р багана нь тэдгээр: `-r-------- 1 root root 60 ... /flag` — эзэн `root`, бүлэг `root`, зөвхөн эзэн уншина. Тиймээс `hacker`-ээр `cat /flag` хийхэд `Permission denied`.
- `chown [username] [file]` — файлын эзэмшигчийг солино. Ердийн үед зөвхөн root ажиллуулж чаддаг; энэ level-д `/challenge/bin/chown`-оор `hacker`-т энэ эрхийг зориуд өгсөн.
- `chown hacker /flag` хийсний дараа `hacker` нь файлын эзэн болж, `r--------`-ийн `r` бит бидэнд хамаарах тул `cat /flag` уншигдана.
- `/challenge/run` нь зөвхөн заавар хэвлэдэг статик скрипт (`cat /challenge/run` → `fold -s <<< "..."`), шалгагч биш. Тиймээс chown хийсний дараа ч, `/challenge/run`-ийн эзнийг сольж үзсэн ч ижил мессеж хэвлэсээр байсан нь алдаа биш.
- Эхэндээ `chmod flag hacker`, `chmod hacker /flag` гэх мэтээр **chmod** (эрх солих) ба **chown** (эзэн солих)-ыг хольж алдсан — `invalid mode` алдаа нь chmod-ийн эхний аргумент mode байх ёстойг сануулна.
- `/flag` гэж шууд ажиллуулахад `Permission denied` — файлд execute бит байхгүй; уншихад `cat` хэрэгтэй. Сүүлийн `chmod +r /flag` нь илүүц алхам — chown-ы дараа эзний `r` бит хангалттай байсан.
- Home директор дахь `flag`, `myflag`, `the-flag`, `not-the-flag -> /flag` зэрэг нь өмнөх level-үүдийн үлдэгдэл файлууд — доорх session-д `ls -la`-ийн урт жагсаалтуудыг `...` мөрөөр товчилсон.

## Solution

```console
hacker@permissions~changing-file-ownership:~$ ls -la
total 84
drwxr-xr-x 1 hacker hacker 410 Sep 20 15:53 .
drwxr-xr-x 1 root root 4096 Jul 24 06:07 ..
... (өмнөх level-үүдийн үлдэгдэл файлууд: flag, myflag, the-flag, not-the-flag -> /flag, ...) ...
hacker@permissions~changing-file-ownership:~$ cd /challenge/
hacker@permissions~changing-file-ownership:/challenge$ ls
Dockerfile bin run
hacker@permissions~changing-file-ownership:/challenge$ ls -a
. .. .init Dockerfile bin run
hacker@permissions~changing-file-ownership:/challenge$ cd bin/
hacker@permissions~changing-file-ownership:/challenge/bin$ ls
chown
hacker@permissions~changing-file-ownership:/challenge/bin$ cd ..
hacker@permissions~changing-file-ownership:/challenge$ cd ..
hacker@permissions~changing-file-ownership:/$ ls
bin boot challenge dev etc flag home lib lib64 media mnt nix opt proc root run sbin srv sys tmp usr var
hacker@permissions~changing-file-ownership:/$ college_file
bash: college_file: command not found
hacker@permissions~changing-file-ownership:/$ /college_file
bash: /college_file: No such file or directory
hacker@permissions~changing-file-ownership:/$ /challenge/run
I have given you access to use the 'chown' command. Use it to enable the flag
to be read!
hacker@permissions~changing-file-ownership:/$ ls -la
total 72
drwxr-xr-x 1 root root 4096 Sep 21 14:28 .
drwxr-xr-x 1 root root 4096 Sep 21 14:28 ..
drwxr-xr-x 1 root root 4096 Sep 21 14:28 challenge
-r-------- 1 root root 60 Sep 21 14:28 flag
drwxr-xr-x 1 root root 4096 Jul 24 06:07 home
... (бусад системийн директорууд) ...
hacker@permissions~changing-file-ownership:/$ chmod flag hacker
chmod: invalid mode: ‘flag’
Try 'chmod --help' for more information.
hacker@permissions~changing-file-ownership:/$ chmod /flag hacker
chmod: invalid mode: ‘/flag’
Try 'chmod --help' for more information.
hacker@permissions~changing-file-ownership:/$ chmod /flag
chmod: missing operand after ‘/flag’
Try 'chmod --help' for more information.
hacker@permissions~changing-file-ownership:/$ chmod hacker /flag
chmod: invalid mode: ‘hacker’
Try 'chmod --help' for more information.
hacker@permissions~changing-file-ownership:/$ chown hacker /flag
hacker@permissions~changing-file-ownership:/$ /challenge/run
I have given you access to use the 'chown' command. Use it to enable the flag
to be read!
hacker@permissions~changing-file-ownership:/$ chown hacker /challenge/run
hacker@permissions~changing-file-ownership:/$ /challenge/run
I have given you access to use the 'chown' command. Use it to enable the flag
to be read!
hacker@permissions~changing-file-ownership:/$ chow root /challenge/run
bash: chow: command not found
hacker@permissions~changing-file-ownership:/$ chown root /challenge/run
hacker@permissions~changing-file-ownership:/$ /challenge/run
I have given you access to use the 'chown' command. Use it to enable the flag
to be read!
hacker@permissions~changing-file-ownership:/$ cat /challenge/run
#!/bin/bash

fold -s <<< "I have given you access to use the 'chown' command. Use it to enable the flag to be read!"
hacker@permissions~changing-file-ownership:/$ chown hacker /college-file
chown: cannot access '/college-file': No such file or directory
hacker@permissions~changing-file-ownership:/$ /flag
bash: /flag: Permission denied
hacker@permissions~changing-file-ownership:/$ chmod +r /flag
hacker@permissions~changing-file-ownership:/$ /flag
bash: /flag: Permission denied
hacker@permissions~changing-file-ownership:/$ cat /flag
pwn.college{AkMk1O3hRkrCZfElNjgn_7AtKuj.QXxEjN0wyMwEzM2EzW}
hacker@permissions~changing-file-ownership:/$
```

## Flag

```
pwn.college{AkMk1O3hRkrCZfElNjgn_7AtKuj.QXxEjN0wyMwEzM2EzW}
```
