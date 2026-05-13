# Searching Manuals

> Module: **Linux Luminarium / Digesting Documentation** · Challenge: `searching-manuals`

`man challenge` командаар challenge-ийн man page-ийг нээж, бичигдсэн нууц аргументыг олж ашиглах сорилт. Энэ удаа аргументын нэр бүр өөр өөр (`--uzi`) байна.

## Тайлбар

| Команд | Тайлбар |
|--------|---------|
| `ls` | Гэрийн санд байгаа файлуудыг харуулна — туршилтын файлууд (`flag.md`, `not-the-flag` гэх мэт) байгаа. |
| `cd /challenge/` | `/challenge` сан руу шилжиж, бинарийг олно. |
| `./challenge` | Аргументгүй ажиллуулахад "read the challenge man page!" гэж шаардана. |
| `man ./challenge` | Буруу — `man` нь зам хүлээдэггүй, нэрийг хайдаг. Permission denied. |
| `man challenge` | Зөв — challenge-ийн man page-ийг нээнэ. Тэндээс `--uzi` аргументыг олно. |
| `./challenge --uzi` | Man page-аас олсон нууц аргументаар flag-ийг авна. |

## Solution

```console
hacker@man~searching-manuals:~$ ls
Desktop  a  flag.md  leap  not-the-flag  rsa  rsa.pub
hacker@man~searching-manuals:~$ cd /challenge/
hacker@man~searching-manuals:/challenge$ ls
Dockerfile  challenge
hacker@man~searching-manuals:/challenge$ ./challenge
Initializing...
Incorrect usage! Please read the challenge man page!
hacker@man~searching-manuals:/challenge$ man ./challenge
/run/dojo/bin/man: can't open ./challenge: Permission denied
hacker@man~searching-manuals:/challenge$ man challenge
hacker@man~searching-manuals:/challenge$ ./challenge --uzi
Initializing...
Correct usage! Your flag: pwn.college{IskxkMsHGggWkrUbcXfNlXMMtbU.QX1EDO0wyMwEzM2EzW}
```

## Гол сургамж

`man <program-name>` — зам биш нэрийг дамжуулна. Challenge тутамд нууц аргументын нэр санамсаргүй (энэ удаад `--uzi`), тиймээс ялгасан флаг бүрийг man page-аас уншиж олох ёстой.

## Flag

```
pwn.college{IskxkMsHGggWkrUbcXfNlXMMtbU.QX1EDO0wyMwEzM2EzW}
```
