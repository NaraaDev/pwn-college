# Implicit Relative Paths

> Module: **Linux Luminarium / Pondering Paths** · Challenge: `implicit-relative-path`

`./` тэмдэглэгээ яагаад зайлшгүй вэ? Bash одоогийн директор дотроос програм автоматаар хайдаггүйн учир.

## Тайлбар

- `run` — Bash зөвхөн `$PATH` хувьсагч доторх директоруудаас хайна. Одоогийн директор `$PATH`-д байхгүй учир **олдохгүй** → `command not found`.
- `./run` — `.` гэдэг тэмдэгт нь "одоогийн директор" гэсэн **тодорхой** заавар. Тиймээс олдоно.
- Шалтгаан: аюулгүй байдал. Хэрэв `.` `$PATH`-д автоматаар орвол хортой `ls`-ийг танихгүй директорт байрлуулчихаад ажиллуулах эрсдэлтэй.

## Solution

```console
hacker@paths~implicit-relative-path:/challenge$ run
bash: run: command not found
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{cSKVkGei9asT02zaLWzzZ-rP-ys.QXxUTN0wyMwEzM2EzW}
```

## Flag

```
pwn.college{cSKVkGei9asT02zaLWzzZ-rP-ys.QXxUTN0wyMwEzM2EzW}
```
