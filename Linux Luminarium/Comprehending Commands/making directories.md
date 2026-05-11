# Making Directories

> Module: **Comprehending Commands** · Challenge: `making-directories`

`mkdir` командаар `/tmp/pwn` директор болон `touch` командаар `/tmp/pwn/college` файл үүсгэж `/challenge/run` ажиллуулах сорилт.

## Тайлбар

| Команд | Тайлбар |
|--------|---------|
| `mkdir <dir>` | Шинэ директор үүсгэнэ. |
| `touch <file>` | Хоосон файл үүсгэнэ (директор биш). |
| `rm -rf <path>` | Директор болон агуулгыг нь хамт устгана. |
| `/challenge/run` | Хүлээгдэж буй `/tmp/pwn/college` файл байгаа эсэхийг шалгаж flag өгнө. |

Алдааны шийдэл: Эхлээд `mkdir college` гэж **директор** үүсгэсэн боловч `/challenge/run` нь `college` нэртэй **файл** шаардаж байв. Директорыг `rm -rf`-ээр устгаад `touch college`-ээр файл үүсгэв.

## Solution

```console
hacker@commands~making-directories:~$ cd /tmp
hacker@commands~making-directories:/tmp$ mkdir pwn
hacker@commands~making-directories:/tmp$ cd pwn/
hacker@commands~making-directories:/tmp/pwn$ mkdir college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Uh oh! /tmp/pwn/college does not exist. Please use the 'touch' command to create it!

hacker@commands~making-directories:/tmp/pwn$ rm -rf college/
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{McWA8Qxu8euSh_ttyxuMepVGxeG.QXxMDO0wyMwEzM2EzW}
```

## Гол сургамж

`mkdir` нь **директор**, `touch` нь **файл** үүсгэнэ. Сорилт хүлээгдэж буй зүйлийнхээ төрлийг анхааралтай уншаарай.

## Flag

```
pwn.college{McWA8Qxu8euSh_ttyxuMepVGxeG.QXxMDO0wyMwEzM2EzW}
```
