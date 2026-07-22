# Redirecting Errors

> Module: **Linux Luminarium / Practicing Piping** · Challenge: `redirecting-errors`

`>` болон `2>` ашиглан stdout болон stderr-ийг тус тусын файлд дахин чиглүүлнэ.

## Тайлбар

- `/challenge/run > myflag 2> instructions` — challenge программын stdout-ыг `myflag`, stderr-ийг `instructions` файлд тус тусад нь бичнэ.
- `>` нь stdout (file descriptor 1), `2>` нь stderr (file descriptor 2)-ыг чиглүүлнэ.
- Challenge хоёуланг нь зөв файл руу чиглүүлсэн эсэхийг тус тусад нь шалгадаг.
- Шалгалт амжилттай болмогц `myflag` файлын агуулгыг `cat`-аар харахад флаг гарч ирнэ.

## Solution

```console
hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat instructions
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will check that error output is redirected to a specific file path : instructions
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!

[TEST] You should have redirected my stderr to instructions. Checking...

[PASS] The file at the other end of my stderr looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{AkUPr6rW0GvoirxGRX_YNInBbw4.QX3YTN0wyMwEzM2EzW}
```

## Flag

```
pwn.college{AkUPr6rW0GvoirxGRX_YNInBbw4.QX3YTN0wyMwEzM2EzW}
```
