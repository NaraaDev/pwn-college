# Executable Shell Scripts

> Module: **Linux Luminarium / Chaining Commands** · Challenge: `executable-shell-scripts`

Скриптийг `chmod +x`-ээр ажиллуулах эрхтэй болгож, `bash`-гүйгээр `./script.sh` гэж шууд дуудаж флаг авна.

## Тайлбар

- `bash script.sh` нь `bash` командыг `script.sh` аргументтай ажиллуулж, командуудыг stdin-ий оронд файлаас уншуулж байгаа хэрэг.
- Файлд execute бит (`chmod +x`, File Permissions модуль) байвал `bash`-ийг бичих шаардлагагүй — `/home/hacker/script.sh`, `~/script.sh`, эсвэл ажлын директор `/home/hacker` бол `./script.sh` гэж замаар нь шууд дуудна.
- `./` заавал хэрэгтэй: `script.sh` гэж бичвэл shell `PATH`-аас хайх тул одоогийн директор дахь файлыг олохгүй.
- `echo '/challenge/solve' > script.sh` → `chmod +x script.sh` → `./script.sh` гэсэн гурван алхмаар флаг гарна.

## Solution

```console
hacker@chaining~executable-shell-scripts:~$ echo '/challenge/solve' > script.sh
hacker@chaining~executable-shell-scripts:~$ chmod +x script.sh
hacker@chaining~executable-shell-scripts:~$ ./script.sh
Congratulations on your shell script execution! Your flag:
pwn.college{UR_NMl7DP4rpdb0GaEfuygt1_FT.QX0cjM1wyMwEzM2EzW}
```

## Flag

```
pwn.college{UR_NMl7DP4rpdb0GaEfuygt1_FT.QX0cjM1wyMwEzM2EzW}
```
