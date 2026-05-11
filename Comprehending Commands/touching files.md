# Touching Files

> Module: **Comprehending Commands** · Challenge: `touching-files`

`touch` — хоосон файл үүсгэх (эсвэл байгаа файлын огноог шинэчлэх).

## Тайлбар

- `touch <file>` — хэрэв `<file>` байхгүй бол хоосон файл шинээр үүсгэнэ. Байгаа бол `mtime`-г шинэчилнэ.
- `rm -rf <file>` — устгана (`-r` recursive, `-f` force).
- Challenge: `/tmp` доор `pwn` болон `college` нэртэй хоёр файлыг үүсгэх ёстой.

```bash
touch /tmp/pwn /tmp/college    # хоёрыг нэг мөрөнд
```

## Solution

```console
hacker@commands~touching-files:~$ cd /tmp/
hacker@commands~touching-files:/tmp$ touch pwn
hacker@commands~touching-files:/tmp$ touch college
hacker@commands~touching-files:/tmp$ /challenge/run
Success! Here is your flag:
pwn.college{w20vcFItCqzb7xZJ4Ufb1lFCLA7.QXwMDO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{w20vcFItCqzb7xZJ4Ufb1lFCLA7.QXwMDO0wyMwEzM2EzW}
```
