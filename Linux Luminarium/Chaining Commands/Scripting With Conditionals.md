# Scripting With Conditionals

> Module: **Linux Luminarium / Chaining Commands** · Challenge: `scripting-with-conditionals`

`if [ "$1" = "pwn" ]` нөхцөлтэй `/home/hacker/solve.sh` бичиж, аргумент `pwn` үед л `college` хэвлүүлж флаг авна.

## Тайлбар

- Bash-ийн `if` синтакс: `if [ нөхцөл ]`, `then`, команд, `fi` — тус бүр тусдаа мөрөнд, эсвэл `;`-ээр тусгаарлагдсан байх ёстой. `[`-ийн дараа болон `]`-ийн өмнө **зай заавал** — `[` нь үнэндээ `test` команд, `]` нь түүний сүүлийн аргумент. Төгсгөл нь `endif` биш `fi` (`if` урвуугаар).
- Эхний оролдлогууд бүтэлгүйтсэн шалтгаан: (1) backtick — command substitution учир shell тэр дор нь ажиллуулахыг оролдож syntax error; (2) `"pwn"]` — `]`-ийн өмнө зайгүй; (3) `if ... then ... fi` бүгд нэг мөрөнд, `;`-гүй → `unexpected end of file`.
- Зассан хувилбар: `printf '#!/bin/bash\nif [ "$1" = "pwn" ]; then\n echo "college"\nfi\n'` — `printf`-ийн `\n` мөр таслах, `; then`-ээр `if`-ийг `then`-тэй нэг мөрөнд бичих боломжтой. `=` ба `==` хоёулаа `[` дотор string тэнцүү эсэхийг шалгана.
- `else` байхгүй тул бусад аргументад юу ч хэвлэхгүй — яг шаардлага. Бусад нөхцөлүүдийг (тоо харьцуулах, файл байгаа эсэх г.м.) `help test`-ээс үзэж болно.

## Solution

```console
hacker@chaining~scripting-with-conditionals:~$ echo `if [ "$1" == "pwn"] then echo "college" fi` > /home/hacker/solve.sh
bash: command substitution: line 2: syntax error: unexpected end of file from `if' command on line 1
hacker@chaining~scripting-with-conditionals:~$ echo 'if [ "$1" == "pwn"] then echo "college" fi' > /home/hacker/solve.sh
hacker@chaining~scripting-with-conditionals:~$ bash solve.sh
solve.sh: line 2: syntax error: unexpected end of file from `if' command on line 1
hacker@chaining~scripting-with-conditionals:~$ bash solve.sh pwn
solve.sh: line 2: syntax error: unexpected end of file from `if' command on line 1
hacker@chaining~scripting-with-conditionals:~$ cat solve.sh
if [ "$1" == "pwn"] then echo "college" fi
hacker@chaining~scripting-with-conditionals:~$ echo 'if [ "$1" == "pwn"] then echo "college" fi' > /home/hacker/solve.sh
hacker@chaining~scripting-with-conditionals:~$ echo 'if [ "$1" == "pwn"] then echo "college" fi' > /home/hacker/solve.sh
hacker@chaining~scripting-with-conditionals:~$ printf '#!/bin/bash\nif [ "$1" = "pwn" ]; then\n echo "college"\nfi\n' > /home/hacker/solve.sh
hacker@chaining~scripting-with-conditionals:~$ chmod +x /home/hacker/solve.sh
hacker@chaining~scripting-with-conditionals:~$ bash solve.sh
hacker@chaining~scripting-with-conditionals:~$ bash solve.sh pwn
college
hacker@chaining~scripting-with-conditionals:~$ bash solve.sh a
hacker@chaining~scripting-with-conditionals:~$ /challenge/run
Correct! Your script properly handles all the conditions.
Here's your flag:
pwn.college{UfSL0h9B_JtFKId_xnR5deLFcqW.0lNzMDOxwyMwEzM2EzW}
```

## Flag

```
pwn.college{UfSL0h9B_JtFKId_xnR5deLFcqW.0lNzMDOxwyMwEzM2EzW}
```
