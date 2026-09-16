# Reading Files

> Module: **Linux Luminarium / Shell Variables** · Challenge: `reading-files`

`read`-ийн stdin-ийг `<` оролт чиглүүлэлтээр файл руу залж, файлын агуулгыг хувьсагчид онооно.

## Тайлбар

- `read PWN < /challenge/read_me` — `<` нь `/challenge/read_me` файлыг `read`-ийн stdin болгож, эхний мөрийг нь `PWN` хувьсагчид онооно.
- `cat /challenge/read_me | read PWN` гэж пайпдах нь **ажиллахгүй**: пайпын баруун тал subshell-д ажиллах тул `PWN` одоогийн shell-д үлдэхгүй. Тиймээс `<` чиглүүлэлт ашиглана.
- `PWN=$(cat /challenge/read_me)` гэж бас болох ч challenge нь `read`-ийг файлтай хослуулж сургахыг зорьсон.

## Solution

```console
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{8o6JF-QoYlyfGKOGiQtZ0-Gt6Fw.QXwIDO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{8o6JF-QoYlyfGKOGiQtZ0-Gt6Fw.QXwIDO0wyMwEzM2EzW}
```
