# Reading Shell Scripts

> Module: **Linux Luminarium / Chaining Commands** · Challenge: `reading-shell-scripts`

`/challenge/run`-ийг `cat`-аар уншиж hardcoded нууц үг (`hack the PLANET`)-ийг олоод, скриптийг **шууд** ажиллуулж флаг авна.

## Тайлбар

- Linux дээрх олон программ shell script байдаг тул кодыг нь уншиж яаж ажилладгийг ойлгож болно. `file /challenge/run` → `setuid a /usr/bin/exec-suid -- /bin/bash -p script, ASCII text executable` — текст файл, хүн уншиж болно (machine code бол `cat`-аар уншигдахгүй).
- `cat /challenge/run`: `read GUESS` — stdin-ээс мөр уншаад `"hack the PLANET"`-тай харьцуулж, таарвал `cat /flag` хийдэг. Нууц үг скриптэд шууд бичигдсэн.
- Анхны алдаа: `bash /challenge/run hack the PLANET` — нууц үгийг **аргументаар** өгсөн боловч скрипт `read`-ээр stdin-ээс уншдаг тул дараагийн мөрөнд гараас дахин бичих шаардлагатай болсон. Хариулт таарсан ч `cat: /flag: Permission denied` — `bash /challenge/run` гэж дуудахад shebang (`#!/usr/bin/exec-suid -- /bin/bash -p`) ашиглагдахгүй, скрипт **hacker** эрхээр ажиллаж `/flag`-ийг (`-r-------- root root`) уншиж чадахгүй.
- `chmod +r /flag`, `chmod +x /flag` — файлын эзэн `root` тул `Operation not permitted`.
- Шийдэл: `/challenge/run`-ийг **шууд** ажиллуулах — SUID shebang-аар root эрхээр ажиллаж, `hack the PLANET` гэж оруулахад `cat /flag` амжилттай болно.
- Хуулсан session-ийн эхэнд өмнөх level-ийн (`scripting-with-multiple-conditions`) үлдэгдэл байсныг хассан.

## Solution

```console
hacker@chaining~reading-shell-scripts:~$ file /challenge/run
/challenge/run: setuid a /usr/bin/exec-suid -- /bin/bash -p script, ASCII text executable
hacker@chaining~reading-shell-scripts:~$ bash /challenge/run
3
Read the /challenge/run file to figure out the correct password!
hacker@chaining~reading-shell-scripts:~$ cat /challenge/run
#!/usr/bin/exec-suid -- /bin/bash -p

read GUESS
if [ "$GUESS" == "hack the PLANET" ]
then
echo "CORRECT! Your flag:"
cat /flag
else
echo "Read the /challenge/run file to figure out the correct password!"
fi
hacker@chaining~reading-shell-scripts:~$ bash /challenge/run hack the PLANET
hack the PLANET
CORRECT! Your flag:
cat: /flag: Permission denied
hacker@chaining~reading-shell-scripts:~$ ls -l /flag
-r-------- 1 root root 61 Sep 22 16:37 /flag
hacker@chaining~reading-shell-scripts:~$ chmod +r /flag
chmod: changing permissions of '/flag': Operation not permitted
hacker@chaining~reading-shell-scripts:~$ ls -l /flag
-r-------- 1 root root 61 Sep 22 16:37 /flag
hacker@chaining~reading-shell-scripts:~$ chmod +a /flag
chmod: invalid mode: ‘+a’
Try 'chmod --help' for more information.
hacker@chaining~reading-shell-scripts:~$ chmod +x /flag
chmod: changing permissions of '/flag': Operation not permitted
hacker@chaining~reading-shell-scripts:~$ ls -l /flag
-r-------- 1 root root 61 Sep 22 16:37 /flag
hacker@chaining~reading-shell-scripts:~$ /challenge/run
hack the PLANET
CORRECT! Your flag:
pwn.college{gMY32KUQ2w2WYQ53DyQ6ldWZ2Dd.0lMwgDOxwyMwEzM2EzW}
hacker@chaining~reading-shell-scripts:~$
```

## Flag

```
pwn.college{gMY32KUQ2w2WYQ53DyQ6ldWZ2Dd.0lMwgDOxwyMwEzM2EzW}
```
