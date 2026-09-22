# Handling Failure

> Module: **Linux Luminarium / Chaining Commands** · Challenge: `handling-failure`

`||`-ээр `/challenge/first-failure` бүтэлгүйтсэн (exit code ≠ 0) үед `/challenge/second`-ийг ажиллуулж флаг авна.

## Тайлбар

- `command1 || command2` — "OR" оператор, `&&`-ийн эсрэг: command1 **бүтэлгүйтсэн** (exit code 0-ээс ялгаатай) үед л command2 ажиллана. Эхнийх амжилттай бол хоёр дахь нь алгасагдана.
- Fallback болон алдаа боловсруулахад тохиромжтой: `touch /file || echo "touch failed"` — `touch` бүтэлгүйтэхэд л мессеж хэвлэнэ; `touch /home/hacker/file || echo ...` амжилттай тул `echo` ажиллахгүй.
- `/challenge/first-failure` зориуд алдааны кодоор гардаг тул `||`-оор залгахад `/challenge/second` ажиллаж флагийг хэвлэнэ.

## Solution

```console
hacker@chaining~handling-failure:~$ /challenge/first-failure || /challenge/second
Nice chaining! Flag: pwn.college{Aqdg8dOH84pBjDx7BcwejuLybGh.01M0MDOxwyMwEzM2EzW}
hacker@chaining~handling-failure:~$
```

## Flag

```
pwn.college{Aqdg8dOH84pBjDx7BcwejuLybGh.01M0MDOxwyMwEzM2EzW}
```
