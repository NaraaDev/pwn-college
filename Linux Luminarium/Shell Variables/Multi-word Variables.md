# Multi-word Variables

> Module: **Linux Luminarium / Shell Variables** · Challenge: `multi-word-variables`

Зай агуулсан (олон үгтэй) утгыг хашилтад хийж хувьсагчид онооно.

## Тайлбар

- `PWN="COLLEGE YEAH"` — утга нь зайтай тул `"..."` (эсвэл `'...'`) хашилтанд хийнэ. Хашилт нь зайгаар тусгаарлагдсан үгсийг **нэг утга** болгон бүлэглэдэг.
- Хашилтгүй `PWN=COLLEGE YEAH` гэвэл shell нь `PWN=COLLEGE`-ийг зөвхөн дараагийн командын түр орчны хувьсагч, `YEAH`-ийг ажиллуулах команд гэж ойлгоно → `YEAH: command not found`.

## Solution

```console
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{YKrg84PR30feZ4zV_5zzMYwo1g8.QXwYTN0wyMwEzM2EzW}
```

## Flag

```
pwn.college{YKrg84PR30feZ4zV_5zzMYwo1g8.QXwYTN0wyMwEzM2EzW}
```
