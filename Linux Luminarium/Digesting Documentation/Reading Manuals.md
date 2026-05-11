# Reading Manuals

> Module: **Linux Luminarium / Digesting Documentation** · Challenge: `reading-manuals`

`man` командаар challenge-ийн гарын авлагыг уншиж, нууц аргументыг олж ашиглах сорилт.

## Тайлбар

| Команд | Тайлбар |
|--------|---------|
| `man challenge` | `/challenge/challenge` программын man page-ийг нээнэ. Нэр (не зам) дамжуулна. |
| `man /challenge/challenge` | Буруу — `man` нь зам хүлээдэггүй, нэрийг мэдээллийн санаас хайдаг. |
| `/challenge/challenge --cqjqdi 162` | Man page-аас олсон нууц аргументыг зөв утгаар дамжуулна. |

Man page-аас олсон мэдээлэл:
```
--cqjqdi NUM    print the flag if NUM is 162
```

## Solution

```console
hacker@man~reading-manuals:/challenge$ man challenge

CHALLENGE(1)   Challenge Commands   CHALLENGE(1)

NAME
    /challenge/challenge - print the flag!

DESCRIPTION
    Output the flag when called with the right arguments.

    --fortune
        read a fortune
    --version
        output version information and exit
    --cqjqdi NUM
        print the flag if NUM is 162

hacker@man~reading-manuals:/challenge$ /challenge/challenge --cqjqdi 162
Correct usage! Your flag: pwn.college{cVqjY1BK6qdY-Pioj2WaFG5sCJ3.QX0EDO0wyMwEzM2EzW}
```

## Гол сургамж

`man <program-name>` — зам биш нэрийг дамжуулна. Man page дотор `DESCRIPTION` хэсгээс нууц аргументыг олно.

## Flag

```
pwn.college{cVqjY1BK6qdY-Pioj2WaFG5sCJ3.QX0EDO0wyMwEzM2EzW}
```
