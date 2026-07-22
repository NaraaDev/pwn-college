# Grepping Errors

> Module: **Linux Luminarium / Practicing Piping** · Challenge: `grepping-errors`

`2>&1` ашиглан stderr-ийг stdout руу нийлүүлж, дараа нь `|` пайпаар шууд `grep` рүү дамжуулна.

## Тайлбар

- `/challenge/run 2>&1 | grep pwn` — эхлээд `2>&1`-ээр stderr (fd 2)-ийг stdout (fd 1) руу чиглүүлж нэгтгэнэ, дараа нь бүхэлд нь `grep pwn` рүү пайпдана.
- Challenge нь stderr-ийн нөгөө талд яг `grep` процесс байгаа эсэхийг шалгадаг.
- `grep pwn` pattern нь `pwn`-ээр эхэлсэн бүх мөрийг (жишээ нь `pwns`, `pwning`, флаг, `pwn`, `pwned`) шүүж гаргана.

## Solution

```console
hacker@piping~grepping-errors:~$ /challenge/run 2>&1 | grep pwn
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/737jwbhw8ji13x9s88z3wpp8pxaqla92-gnugrep-3.12/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwns
pwning
pwn.college{8DhVk5xEiBizBKOlyytCnp4LUNT.QX1ATO0wyMwEzM2EzW}
pwn
pwned
```

## Flag

```
pwn.college{8DhVk5xEiBizBKOlyytCnp4LUNT.QX1ATO0wyMwEzM2EzW}
```
