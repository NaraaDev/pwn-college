# Redirecting More Output

> Module: **Linux Luminarium / Practicing Piping** · Challenge: `redirecting-more-output`

`/challenge/run` программын стандарт гаралтыг `>`-аар заасан файлд бичиж, дараа нь тухайн файлыг уншиж флагийг авна.

## Тайлбар

- `/challenge/run > myflag` — challenge-ийн шалгагч программын stdout-ыг `myflag` нэртэй файл руу дахин чиглүүлнэ.
- Challenge stdout нь яг тухайн файл руу чиглүүлэгдсэн эсэхийг шалгадаг тул `>` заавал ашиглах шаардлагатай.
- Шалгалт амжилттай болмогц `myflag` файлын агуулгыг `cat`-аар харахад флаг гарч ирнэ.

## Solution

```console
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{8di3IPh1A68PdoJLaUAmpFgNB4D.QX1YTN0wyMwEzM2EzW}
```

## Flag

```
pwn.college{8di3IPh1A68PdoJLaUAmpFgNB4D.QX1YTN0wyMwEzM2EzW}
```
