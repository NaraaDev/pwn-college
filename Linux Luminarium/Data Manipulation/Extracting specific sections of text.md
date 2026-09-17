# Extracting Specific Sections of Text

> Module: **Linux Luminarium / Data Manipulation** · Challenge: `extracting-specific-sections-of-text`

`cut`-аар мөр бүрээс хэрэгтэй баганыг нь салгаж аваад, `tr`-ээр мөрүүдийг нийлүүлж флаг угсарна.

## Тайлбар

- `/challenge/run` нь флагийн хэсгүүдийг мөр бүрд нэмэлт үг дагуулан хэвлэдэг.
- `cut -d " " -f 2` — `-d " "` нь зайг тусгаарлагч (delimiter) болгож, `-f 2` нь мөр бүрийн **2 дахь талбарыг** л авна. Ингэснээр илүү үгс хасагдаж, флагийн хэсэг үлдэнэ.
- `tr -d "\n"` — үлдсэн мөрүүдийн newline-ыг устгаж, хэсгүүдийг нэг мөр болгон залгана.
- `cut` нь `awk '{print $2}'`-тэй төстэй боловч илүү хөнгөн: зөвхөн байрлалаар тасалдаг.

## Solution

```console
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d " " -f 2 | tr -d "\n"
pwn.college{E1A4NjXtQJt6mGPy29DaYnv0ZHv.01NxEzNxwyMwEzM2EzW}
```

## Flag

```
pwn.college{E1A4NjXtQJt6mGPy29DaYnv0ZHv.01NxEzNxwyMwEzM2EzW}
```
