# Intro To Arguments

> Module: **Linux Luminarium / Hello Hackers** · Challenge: `intro-to-arguments`

Коммандуудад **аргумент** дамжуулна. `command arg1 arg2 ...` — комманд гэдэг нь зөвхөн нэр биш, ард нь нэмэлт өгөгдөл (аргумент) дамжуулж болно.

## Тайлбар

- `echo <text>` — өгсөн текстээ буцаагаад терминал руу хэвлэнэ.
- Аргументыг **зайгаар** (space) ялгана. `echo Hello Hackers!` гэвэл `Hello` ба `Hackers!` гэсэн хоёр аргументаар дуудна, гэхдээ `echo` тэдгээрийг нэгтгэж хэвлэнэ.
- Энэ challenge-д `hello` коммандыг `hackers` гэсэн аргументаар дуудах ёстой: `hello hackers`.

## Solution

```console
hacker@hello~intro-to-arguments:~$ echo Hello
Hello
hacker@hello~intro-to-arguments:~$ echo Hello Hackers!
Hello Hackers!
hacker@hello~intro-to-arguments:~$ hello
It looks like you've invoked this command without an argument. Please invoke
this with a single argument of 'hackers'!
hacker@hello~intro-to-arguments:~$ hello hackers
Success! Here is your flag:
pwn.college{81QgccK3M6ns47KxQgI8gUlDf07.QX4YjM1wyMwEzM2EzW}
```

## Flag

```
pwn.college{81QgccK3M6ns47KxQgI8gUlDf07.QX4YjM1wyMwEzM2EzW}
```
