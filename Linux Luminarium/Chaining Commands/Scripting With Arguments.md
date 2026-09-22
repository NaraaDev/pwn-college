# Scripting With Arguments

> Module: **Linux Luminarium / Chaining Commands** · Challenge: `scripting-with-arguments`

`$1`, `$2` аргументуудыг урвуу дарааллаар хэвлэдэг `/home/hacker/solve.sh` бичээд `/challenge/run`-аар шалгуулж флаг авна.

## Тайлбар

- Скрипт аргументуудыг `$1`, `$2`, `$3`, ... тусгай хувьсагчаар авна — `bash myscript.sh hello world` гэвэл `$1`=`hello`, `$2`=`world`.
- Урвуу дараалал: `echo "${2} ${1}"`. `${2}` ба `$2` ижил; хаалт нь хувьсагчийн нэрийг дараагийн тэмдэгтээс тодорхой салгадаг.
- Хашилт: `echo 'echo "${2} ${1}"' >> solve.sh` — гадна талын **нэг** хашилт `$2`, `$1`-ийг тухайн shell дээр өргөтгөхөөс хамгаалж, файлд шууд `${2} ${1}` гэж бичигдэнэ. Давхар хашилт ашигласан бол хоосон утга орох байсан.
- `bash solve.sh 3 4` → `4 3` гэж өөрөө шалгасны дараа `/challenge/run` баталгаажуулж флаг өгнө.

## Solution

```console
hacker@chaining~scripting-with-arguments:~$ echo '#!/bin/bash' > /home/hacker/solve.sh
hacker@chaining~scripting-with-arguments:~$ echo 'echo "${2} ${1}"' >> solve.sh
hacker@chaining~scripting-with-arguments:~$ bash solve.sh 3 4
4 3
hacker@chaining~scripting-with-arguments:~$ /challenge/run
Correct! Your script properly reversed the arguments.
Here's your flag:
pwn.college{UAaK2sGumQD7cJb5uBh0KKNX7JI.0VNzMDOxwyMwEzM2EzW}
hacker@chaining~scripting-with-arguments:~$
```

## Flag

```
pwn.college{UAaK2sGumQD7cJb5uBh0KKNX7JI.0VNzMDOxwyMwEzM2EzW}
```
