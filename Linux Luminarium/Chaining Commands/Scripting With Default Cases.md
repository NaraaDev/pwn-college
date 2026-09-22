# Scripting With Default Cases

> Module: **Linux Luminarium / Chaining Commands** · Challenge: `scripting-with-default-cases`

`if`/`else`-тэй `/home/hacker/solve.sh` — аргумент `pwn` бол `college`, бусад бүх тохиолдолд `nope` хэвлүүлж флаг авна.

## Тайлбар

- `else` нь `if` нөхцөл худал байх үед ажиллана — өөрийн нөхцөлгүй, `then`-гүй, өмнө таараагүй бүхнийг барина. `fi` бүхэл `if/else` бүтцийн төгсгөлд нэг л удаа бичигдэнэ.
- `else` заавал биш — өмнөх level-д байгаагүй; логик шаардсан үед л нэмнэ.
- `printf 'if [ "$1" = "pwn" ]; then\n echo "college"\nelse\n echo "nope"\nfi\n'` — shebang-гүй ч `bash solve.sh` гэж ажиллуулдаг тул асуудалгүй. `bash solve.sh` (аргументгүй, `$1` хоосон) → `nope`, `bash solve.sh pwn` → `college`.

## Solution

```console
hacker@chaining~scripting-with-default-cases:~$ printf 'if [ "$1" = "pwn" ]; then\n echo "college"\nelse\n echo "nope"\nfi\n' > /home/hacker/solve.sh
hacker@chaining~scripting-with-default-cases:~$ bash solve.sh
nope
hacker@chaining~scripting-with-default-cases:~$ bash solve.sh pwn
college
hacker@chaining~scripting-with-default-cases:~$ /challenge/run
Correct! Your script properly handles the if/else conditions.
Here's your flag:
pwn.college{UERZBosRx_zkOnGXxVdITeWx3Gw.01NzMDOxwyMwEzM2EzW}
hacker@chaining~scripting-with-default-cases:~$
```

## Flag

```
pwn.college{UERZBosRx_zkOnGXxVdITeWx3Gw.01NzMDOxwyMwEzM2EzW}
```
