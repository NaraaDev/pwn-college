# Deleting Newlines

> Module: **Linux Luminarium / Data Manipulation** · Challenge: `deleting-newlines`

Мөр мөрөөр тасарсан флагийг `tr -d "\n"`-ээр newline-уудыг нь устган нэг мөр болгож нийлүүлнэ.

## Тайлбар

- `/challenge/run` нь флагийг олон мөр болгон тасалж хэвлэдэг (line-split).
- `tr -d "\n"` — `\n` (newline) тэмдэгтийг бүгдийг нь устгаснаар тасарсан хэсгүүд залгагдаж, бүтэн флаг нэг мөр дээр гарч ирнэ.
- `"\n"` -ийг хашилтанд авах шаардлагатай: `tr` өөрөө `\n`-ийг newline гэж тайлдаг тул shell рүү задруулахгүй байх нь зөв.
- Newline бүгд арилсан тул флагийн дараа shell-ийн prompt шууд залгаж гарч болзошгүй — энэ нь хэвийн.

## Solution

```console
hacker@data~deleting-newlines:~$ /challenge/run | tr -d "\n"
Your line-split flag: pwn.college{IhF_iGQ-JncJNN7JIEQ-1q9b8LH.0VNxEzNxwyMwEzM2EzW}
```

## Flag

```
pwn.college{IhF_iGQ-JncJNN7JIEQ-1q9b8LH.0VNxEzNxwyMwEzM2EzW}
```
