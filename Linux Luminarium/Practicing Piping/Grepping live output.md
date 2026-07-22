# Grepping Live Output

> Module: **Linux Luminarium / Practicing Piping** · Challenge: `grepping-live-output`

`|` пайп ашиглан challenge программын гаралтыг шууд `grep` рүү дамжуулна.

## Тайлбар

- `/challenge/run | grep pwn.college` — challenge программын stdout-ыг файлд бус, шууд `grep` процесс руу пайпаар дамжуулна.
- Challenge нь stdout-ын нөгөө талд яг `grep` гэсэн процесс байгаа эсэхийг шалгадаг (файл биш, өөр процесс байх ёстой).
- Шалгалт амжилттай болмогц флаг шууд гаралтад хэвлэгдэнэ.

## Solution

```console
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/737jwbhw8ji13x9s88z3wpp8pxaqla92-gnugrep-3.12/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{oF6J9gDq17_sPX0IWHLrD5sqgo3.QX5EDO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{oF6J9gDq17_sPX0IWHLrD5sqgo3.QX5EDO0wyMwEzM2EzW}
```
