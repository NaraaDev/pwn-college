# Appending Output

> Module: **Linux Luminarium / Practicing Piping** · Challenge: `appending-output`

`>>` дахин чиглүүлэлт ашиглан challenge программын хоёр удаагийн бичилтийг нэг файлд хуримтлуулна (overwrite биш, append).

## Тайлбар

- `/challenge/run >> /home/hacker/the-flag` — challenge программын stdout-ыг `/home/hacker/the-flag` файлд **append mode**-оор чиглүүлнэ.
- Программ флагийг хоёр хэсэгт хуваан бичдэг: эхний хэсгийг файлд шууд бичиж, хоёр дахь хэсгийг stdout руу бичдэг.
- Хэрэв `>` (overwrite) ашигласан бол хоёр дахь бичилт эхнийхийг дарж, флаг дутуу үлдэнэ. `>>` ашигласнаар хоёр хэсэг нийлж бүтэн флаг болно.

## Solution

```console
hacker@piping~appending-output:~$ /challenge/run >> /home/hacker/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do
the first write directly to the file, and the second write, I'll do to stdout
(if it's pointing at the file). If you redirect the output in append mode, the
second write will append to (rather than overwrite) the first write, and you'll
get the whole flag!
pwn.college{mQZDH-QqX4uzmxrPnDmLQIf.QX3ATO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{mQZDH-QqX4uzmxrPnDmLQIf.QX3ATO0wyMwEzM2EzW}
```
