# Adding Commands

> Module: **Linux Luminarium / Pondering Path** · Challenge: `adding-commands`

Флагийг `cat` хийдэг `win` shell script бичиж, түүний директорийг `PATH`-д оноогоод `/challenge/run`-оор `win`-ийг дуудуулна.

## Тайлбар

- Өмнөх level-д `win` нь `/challenge/more_commands`-д бэлэн байсан. Энэ удаа `win` огт байхгүй (`which win` → `no win in (...)`) — өөрөө бичих ёстой.
- `/challenge/run` root эрхээр ажиллаж `win`-ийг дууддаг тул `win` нь зүгээр л `/flag`-ийг `cat` хийхэд хангалттай.
- Бэрхшээл: `PATH=/home/hacker/scripts` гэж дарж бичвэл `win` доторх `cat` олдохгүй болно. Шийдэл гурав:
  1. `cat`-ийг absolute path-аар (`/bin/cat`) дуудах — энд үүнийг сонгосон.
  2. Хуучин директоруудаа хадгалж шинээ нэмэх: `PATH=$PATH:/home/hacker/scripts`.
  3. `PATH`-аас хамаардаггүй bash builtin `read`-ээр `/flag`-ийг унших.
- `printf '#!/bin/bash\n/bin/cat /flag\n' > .../win` — shebang-тай хоёр мөрт script үүсгээд `chmod +x`-ээр executable болгоно.
- Олон мөрийг нэг дор paste хийсэн тул дараагийн мөрүүд тусдаа prompt-гүй харагдаж байна.

## Solution

```console
hacker@path~adding-commands:~$ win
bash: win: command not found
hacker@path~adding-commands:~$ which win
which: no win in (/run/challenge/bin:/run/dojo/bin:/challenge/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin)
hacker@path~adding-commands:~$ mkdir -p /home/hacker/scripts
printf '#!/bin/bash\n/bin/cat /flag\n' > /home/hacker/scripts/win
chmod +x /home/hacker/scripts/win
PATH=/home/hacker/scripts
/challenge/run
Invoking 'win'....
pwn.college{smv9grWbtbyXSDOT8lM6ocUe2tn.QX2cjM1wyMwEzM2EzW}
hacker@path~adding-commands:~$
```

## Flag

```
pwn.college{smv9grWbtbyXSDOT8lM6ocUe2tn.QX2cjM1wyMwEzM2EzW}
```
