# Searching For Manuals

> Module: **Linux Luminarium / Digesting Documentation** · Challenge: `searching-for-manuals`

Challenge-ийн man page-ийн нэр нь "challenge" биш, өөр санамсаргүй нэртэй (`pghszimahh`) бичигдсэн байдаг. `man -k` (apropos) ашиглан "flag" эсвэл "challenge" түлхүүр үгээр хайж, жинхэнэ man page-ийн нэрийг олох сорилт.

## Тайлбар

| Команд | Тайлбар |
|--------|---------|
| `cd /challenge/bin && ls` | Challenge-ийн өөрийн `man` бинарь энд байна (PATH-ийг хязгаарласан). |
| `man -k flag man` | `-k` / `--apropos` нь man page-ийн нэр болон тайлбараас түлхүүр үг хайна. Олон үр дүн гарна. |
| `man -k challenge` | "challenge" гэх үг агуулсан man page-уудаас зөвхөн `pghszimahh (1) - print the flag!` гарна — энэ бол challenge-ийн жинхэнэ man page. |
| `man --apropos flag challenge` | Хоёр түлхүүр үг хослуулан хайхад `pghszimahh` дээд талд гарна. |
| `man pghszimahh` | Олсон нэрээр man page-ийг нээж, `--pghszi 220` гэсэн аргументыг олно. |
| `./challenge --pghszi 220` | Man page-аас олсон нууц аргумент болон утгыг дамжуулж flag-ийг авна. |

Man page-аас олсон гол хэсэг:

```
NAME
    /challenge/challenge - print the flag!

SYNOPSIS
    challenge OPTION

DESCRIPTION
    Output the flag when called with the right arguments.

    --fortune       read a fortune
    --version       output version information and exit
    --pghszi NUM    print the flag if NUM is 220
```

## Solution

```console
hacker@man~searching-for-manuals:/$ cd challenge/
hacker@man~searching-for-manuals:/challenge$ ls
Dockerfile  bin  challenge
hacker@man~searching-for-manuals:/challenge$ cd bin/
hacker@man~searching-for-manuals:/challenge/bin$ ls
man
hacker@man~searching-for-manuals:/challenge/bin$ man -k challenge
pghszimahh (1) - print the flag!
hacker@man~searching-for-manuals:/challenge/bin$ cd ..
hacker@man~searching-for-manuals:/challenge$ man pghszimahh

CHALLENGE(1)                          Challenge Commands                         CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune       read a fortune
       --version       output version information and exit
       --pghszi NUM    print the flag if NUM is 220

AUTHOR
       Written by Zardus.

hacker@man~searching-for-manuals:/challenge$ ./challenge --pghszi 220
Correct usage! Your flag: pwn.college{IpOYgEThU2S-szLSiUmESNJVahh.QX2EDO0wyMwEzM2EzW}
```

## Гол сургамж

- `man -k <keyword>` (эсвэл `apropos <keyword>`) — man page-ийн **нэр болон тайлбараас** хайдаг. Программын жинхэнэ нэрийг мэдэхгүй үед маш ашигтай.
- `man <program>` нь нэрийг шууд мэдэхгүй бол `man -k` ашиглан "flag" / "challenge" гэх мэт түлхүүр үгээр эхлээд олно.
- Challenge тутамд man page-ийн нэр санамсаргүй (`pghszimahh`), тиймээс шууд `man challenge` гэж бичээд олохгүй — `man -k` ашиглах ёстой.

## Flag

```
pwn.college{IpOYgEThU2S-szLSiUmESNJVahh.QX2EDO0wyMwEzM2EzW}
```
