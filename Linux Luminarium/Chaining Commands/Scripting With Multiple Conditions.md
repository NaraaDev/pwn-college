# Scripting With Multiple Conditions

> Module: **Linux Luminarium / Chaining Commands** · Challenge: `scripting-with-multiple-conditions`

`elif`-ээр олон нөхцөл шалгадаг `/home/hacker/solve.sh` — `hack`→`the planet`, `pwn`→`college`, `learn`→`linux`, бусад→`unknown` хэвлүүлж флаг авна.

## Тайлбар

- `elif` (else if) — `if` нөхцөл худал бол дараагийн нөхцөлийг шалгана; `if`-тэй адил `then` заавал хэрэгтэй. Төгсгөлийн `else` бүх таараагүй тохиолдлыг барина, `fi` бүхлээр нь хаана.
- Нөхцөлүүд дарааллаар шалгагдана: эхний үнэн нөхцөлийн блок л ажиллаад бусад нь алгасагдана.
- Зай: `[` ба `]` бусад тэмдэгтээс зайгаар тусгаарлагдсан байх ёстой (`[ "$1" = "hack" ]`), эс бөгөөс bash нөхцөлийг задлан шинжилж чадахгүй.
- `printf`-ийн `\n`-ээр `if`/`elif`/`else`/`fi`-г тусдаа мөрөнд бичиж нэг командаар скрипт үүсгээд `/challenge/run`-аар шалгуулсан.

## Solution

```console
hacker@chaining~scripting-with-multiple-conditions:~$ printf 'if [ "$1" = "hack" ]; then\n echo "the planet"\nelif [ "$1" = "pwn" ]; then\n echo "college"\nelif [ "$1" = "learn" ]; then\n echo "linux"\nelse\n echo "unknown"\nfi\n' > /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ /challenge/run
Correct! Your script properly handles all the conditions with elif.
Here's your flag:
pwn.college{4duQY5Vfmv08uqYc8QLRo10D6rU.0FOzMDOxwyMwEzM2EzW}
hacker@chaining~scripting-with-multiple-conditions:~$
```

## Flag

```
pwn.college{4duQY5Vfmv08uqYc8QLRo10D6rU.0FOzMDOxwyMwEzM2EzW}
```
