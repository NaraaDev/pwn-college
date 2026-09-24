# Setting PATH

> Module: **Linux Luminarium / Pondering Path** · Challenge: `setting-path`

`PATH`-ийг `/challenge/more_commands` болгож, `/challenge/run` нь `win` командыг bare нэрээр нь олох боломжтой болгоод флаг авна.

## Тайлбар

- Стандарт бус газар байгаа програмыг ихэвчлэн бүтэн path-аар нь (`/home/hacker/scripts/goodscript`) ажиллуулах шаардлагатай — bare нэрээр (`goodscript`) дуудвал `command not found`.
- Директорийг `PATH`-д нэмэх эсвэл `PATH`-ийг түүгээр солих үед тэнд байгаа програмуудыг bare нэрээр нь ажиллуулж болно: `PATH=/home/hacker/scripts` → `goodscript`.
- `/challenge/run` нь `win`-ийг bare нэрээр дууддаг, харин `win` нь `PATH`-д байхгүй `/challenge/more_commands/` дотор байна. `/challenge/run`-д зөвхөн `win` хэрэгтэй тул `PATH=/challenge/more_commands` гэж бүхэлд нь дарж бичихэд хангалттай (transcript-д энэ мөр хуулагдаагүй).

## Solution

```console
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{Y_7Qbwsu0BUM4iIEw1onVPgdU6P.QX1cjM1wyMwEzM2EzW}
```

## Flag

```
pwn.college{Y_7Qbwsu0BUM4iIEw1onVPgdU6P.QX1cjM1wyMwEzM2EzW}
```
