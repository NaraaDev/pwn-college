# Redirecting Script Output

> Module: **Linux Luminarium / Chaining Commands** · Challenge: `redirecting-script-output`

`/challenge/pwn`, `/challenge/college`-ийг дуудах `x.sh` скриптийн гаралтыг `bash x.sh | /challenge/solve`-оор нэг команд руу pipe хийж флаг авна.

## Тайлбар

- Shell-ийн хувьд скрипт бол ердийн команд — Piping модулийн бүх redirection (`>` stdout, `2>` stderr, `<` stdin, `>>`/`2>>` append, `>&` өөр file descriptor, `|` pipe) түүн дээр ажиллана. `bash script.sh > output` гэвэл скриптийн бүх гаралт файлд орно.
- Хэд хэдэн программын гаралтыг **нэг** команд руу дамжуулах энгийн арга: тэдгээрийг скриптэд бичээд скриптийн гаралтыг pipe-лана. `bash x.sh | /challenge/solve` — `/challenge/pwn` ба `/challenge/college`-ийн гаралт хоёулаа `/challenge/solve`-ийн stdin-д нэг урсгалаар очно.
- Executable script дараагийн level-д гарах тул энд скриптийг `bash`-аар ажиллуулж байна.

## Solution

```console
hacker@chaining~redirecting-script-output:~$ echo '/challenge/pwn' > x.sh
hacker@chaining~redirecting-script-output:~$ echo '/challenge/college' >> x.sh
hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{8SAtuhtveawTgv10R3nmAHKnFD_.QX4ETO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{8SAtuhtveawTgv10R3nmAHKnFD_.QX4ETO0wyMwEzM2EzW}
```
