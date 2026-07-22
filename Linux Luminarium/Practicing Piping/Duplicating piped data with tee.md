# Duplicating Piped Data With tee

> Module: **Linux Luminarium / Practicing Piping** · Challenge: `duplicating-piped-data-with-tee`

`tee` ашиглан пайпаар дамжиж буй өгөгдлийг өөрчлөлгүй дараагийн процесс руу дамжуулна.

## Тайлбар

- `/challenge/pwn --secret cwHzbCyN | tee | /challenge/college` — `/challenge/pwn` командын гаралтыг `tee`-ээр дамжуулж, `tee` нь ирсэн өгөгдлөө хэвлэхийн зэрэгцээ (энд аргументгүй тул зөвхөн stdout) дараагийн `/challenge/college` процесс руу яг хэвээр дамжуулна.
- `secret` утга (`cwHzbCyN`) хоёр процессын хооронд өөрчлөгдөлгүй дамжсан тул `/challenge/college` зөв хүлээн авч баталгаажуулав.

## Solution

```console
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret cwHzbCyN | tee | /challenge/college
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{cwHzbCyN-arGoIgM7aGCDlywICK.QXxITO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{cwHzbCyN-arGoIgM7aGCDlywICK.QXxITO0wyMwEzM2EzW}
```
