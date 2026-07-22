# Grepping Stored Results

> Module: **Linux Luminarium / Practicing Piping** · Challenge: `grepping-stored-results`

`grep` ашиглан `/tmp/data.txt` файл дотроос флаг агуулсан мөрийг олж хайна.

## Тайлбар

- `/tmp/data.txt` файл нь маш олон мөр агуулж байгаа тул флагийг гараар хайхын оронд `grep`-ээр шүүнэ.
- Флаг `pwn.college{...}` хэлбэртэй бөгөөд `{` `}` тэмдэгтүүдийг агуулдаг тул тэдгээрийг таарах pattern-аар хайж олов.

## Solution

```console
hacker@piping~grepping-stored-results:~$ grep {*} /tmp/data.txt
pwn.college{wZlbtUre4unUBhGKC6bDrf4w39P.QX4EDO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{wZlbtUre4unUBhGKC6bDrf4w39P.QX4EDO0wyMwEzM2EzW}
```
