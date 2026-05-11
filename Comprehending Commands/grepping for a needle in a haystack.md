# Grepping for a Needle in a Haystack

> Module: **Comprehending Commands** · Challenge: `grepping-for-a-needle-in-a-haystack`

Том файлаас нэг мөрийг хайх — `grep` ашиглана.

## Тайлбар

- `grep <pattern> <file>` — өгсөн файлаас pattern (хэв)-тэй тохирох мөрүүдийг хэвлэнэ.
- Энэ challenge-ийн `data.txt` маш том файл. Дотроо нэг л мөрөнд `pwn.college{...}` байгаа.
- Pattern-д `pwn.college` өгөхөд тохирох мөрийг буцаана.

```bash
grep pwn.college /challenge/data.txt
grep -i error log.txt        # -i: том/жижиг үсэг хайхгүй
grep -r TODO src/            # -r: дотор дотроо хайх
grep -n pattern file         # -n: мөрийн дугаар хэвлэх
```

## Solution

```console
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{4tKOhz7rmzFYrUmmcFqcslYhO8y.QX3EDO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{4tKOhz7rmzFYrUmmcFqcslYhO8y.QX3EDO0wyMwEzM2EzW}
```
