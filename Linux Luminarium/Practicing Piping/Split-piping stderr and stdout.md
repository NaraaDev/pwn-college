# Split-Piping stderr And stdout

> Module: **Linux Luminarium / Practicing Piping** · Challenge: `split-piping-stderr-and-stdout`

`>(...)` процесс орлуулалт ашиглан stdout ба stderr-ийг тус тусдаа өөр өөр программ руу зэрэг чиглүүлнэ.

## Тайлбар

- `/challenge/hack > >(/challenge/planet) 2> >(/challenge/the)` — `/challenge/hack`-ийн stdout-ыг `>(...)` процесс орлуулалтаар `/challenge/planet` рүү, stderr (`2>`)-ийг өөр `>(...)` орлуулалтаар `/challenge/the` рүү тус тусад нь чиглүүлнэ.
- Ердийн `>` / `2>` файл руу чиглэдэг бол энд файлын оронд ажиллаж буй процесс байрлуулж, хоёр stream-ийг зэрэг өөр өөр программд дамжуулж байгаа нь давуу тал.

## Solution

```console
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack > >(/challenge/planet) 2> >(/challenge/the)
Congratulations, you have learned a redirection technique that even experts
struggle with! Here is your flag:
pwn.college{snI4fxWPNFlxCRo22rCxmaGkQWl.QXxQDM2wyMwEzM2EzW}
```

## Flag

```
pwn.college{snI4fxWPNFlxCRo22rCxmaGkQWl.QXxQDM2wyMwEzM2EzW}
```
