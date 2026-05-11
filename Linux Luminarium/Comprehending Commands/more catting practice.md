# More Catting Practice

> Module: **Comprehending Commands** · Challenge: `more-catting-practice`

`cd` ашиглахгүйгээр **absolute path**-аар flag файлыг унших.

## Тайлбар

- Challenge `cd` ашиглахыг хориглож байна. Тиймээс file-руугаа очихгүй, **зам нь өөрөө орох ёстой**.
- Flag-ийн байрлал: `/usr/lib/mime/flag`.
- `cat /usr/lib/mime/flag` — absolute path-аар хол байрласан файлыг ч `cat`-аар уншиж чадна.

## Solution

```console
hacker@commands~more-catting-practice:~$ cd ..
You used 'cd'! In this level, I don't allow you to change the working directory
--- you MUST pass 'cat' the absolute path (/usr/lib/mime/flag).
hacker@commands~more-catting-practice:~$ cat /usr/lib/mime/flag
pwn.college{wJgKfVe1lXoI0JXSTDPGMUhhBce.QXwITO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{wJgKfVe1lXoI0JXSTDPGMUhhBce.QXwITO0wyMwEzM2EzW}
```
