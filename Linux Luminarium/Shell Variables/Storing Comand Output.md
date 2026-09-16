# Storing Command Output

> Module: **Linux Luminarium / Shell Variables** · Challenge: `storing-command-output`

`$(...)` команд орлуулалт ашиглан командын гаралтыг хувьсагчид хадгална.

## Тайлбар

- `PWN=$(/challenge/run)` — `$(...)` дотор байгаа командыг ажиллуулж, түүний **stdout**-ыг `PWN` хувьсагчид онооно (command substitution).
- `/challenge/run` флагаа stdout руу хэвлэсэн тул тэр нь `PWN`-д орсон; "Congratulations..." мессеж нь stdout биш тул хувьсагчид ороогүй, дэлгэцэнд шууд гарсан.
- `echo "$PWN"` — хадгалсан утгыг хэвлэнэ. Хашилт нь утга дахь зай, шинэ мөрийг хэвээр хадгалахад тустай.
- Хуучин хэлбэр нь backtick `` `command` `` боловч `$(...)` нь давхарлаж болдог, уншихад ойлгомжтой.

## Solution

```console
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out
and submit it!
hacker@variables~storing-command-output:~$ echo "$PWN"
pwn.college{Id6p3ozKuXut8Gea7uVpUK0PKWm.QX1cDN1wyMwEzM2EzW}
```

## Flag

```
pwn.college{Id6p3ozKuXut8Gea7uVpUK0PKWm.QX1cDN1wyMwEzM2EzW}
```
