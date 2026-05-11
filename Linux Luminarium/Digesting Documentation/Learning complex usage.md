# Learning Complex Usage

> Module: **Linux Luminarium / Digesting Documentation** · Challenge: `learning-complex-usage`

`--printfile` аргументаар дурын файлын агуулгыг хэвлүүлж болдог программыг ашиглан `/flag` файлыг уншуулах сорилт.

## Тайлбар

| Команд | Тайлбар |
|--------|---------|
| `/challenge/challenge --printfile <path>` | Заасан файлын агуулгыг хэвлэнэ. Зөв зам дамжуулах шаардлагатай. |
| `touch flag.md` | Туршилтаар файл үүсгэсэн — гэхдээ хоосон учир flag агуулаагүй. |

Алдааны тайлбар:
- `--printfile /challenge/DESCRIPTION.md` → файл байхгүй тул хоосон
- `--printfile /home/hacker/flag.md` → файл байгаа ч хоосон (өөрөө үүсгэсэн)
- `--printfile /flag` → `/flag` системийн flag файл — зөв хариу

## Solution

```console
hacker@man~learning-complex-usage:/$ /challenge/challenge --printfile /challenge/DESCRIPTION.md
Correct argument! Here is the /challenge/DESCRIPTION.md file:
cat: /challenge/DESCRIPTION.md: No such file or directory

hacker@man~learning-complex-usage:~$ touch flag.md
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /home/hacker/flag.md
Correct argument! Here is the /home/hacker/flag.md file:
(хоосон — flag агуулаагүй)

hacker@man~learning-complex-usage:/$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{oEyO3fFcL2Xc929fAJ_s4mSuTvF.QX1ITO0wyMwEzM2EzW}
```

## Гол сургамж

`--printfile` нь аргументаар заасан файлыг уншдаг тул `/flag` — системийн жинхэнэ flag файлын замыг шууд дамжуулах хэрэгтэй.

## Flag

```
pwn.college{oEyO3fFcL2Xc929fAJ_s4mSuTvF.QX1ITO0wyMwEzM2EzW}
```
