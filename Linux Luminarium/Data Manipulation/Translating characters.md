# Translating Characters

> Module: **Linux Luminarium / Data Manipulation** · Challenge: `translating-characters`

`tr`-ээр тэмдэгтийг нэг олонлогоос нөгөө рүү хөрвүүлж, том/жижиг үсэг нь солигдсон флагийг сэргээнэ.

## Тайлбар

- `/challenge/run` нь флагийг том/жижиг үсгийг нь урвуулж (case-swapped) хэвлэдэг.
- `tr 'A-Za-z' 'a-zA-Z'` — эхний олонлогийн тэмдэгт бүрийг хоёр дахь олонлогийн ижил байрлалд буй тэмдэгтээр солино: `A→a`, `B→b`, … `a→A`, `b→B`. Ингэснээр урвуулсан үсгийн том/жижиг байдал буцаж хэвэндээ орно.
- `tr` нь зөвхөн **stdin**-ээс уншдаг тул файлын нэрийг аргумент болгож авахгүй — заавал пайпаар дамжуулна.

## Solution

```console
hacker@data~translating-characters:~$ /challenge/run | tr 'A-Za-z' 'a-zA-Z'
yOUR CASE-SWAPPED FLAG:
pwn.college{sh0kbfzHwjnq3yibs__8Znf_UCZ.01MxEzNxwyMwEzM2EzW}
```

## Flag

```
pwn.college{sh0kbfzHwjnq3yibs__8Znf_UCZ.01MxEzNxwyMwEzM2EzW}
```
