# Extracting the First Lines With head

> Module: **Linux Luminarium / Data Manipulation** · Challenge: `extracting-the-first-lines-with-head`

`head -n` ашиглан гаралтын эхний N мөрийг л салгаж аваад дараагийн программ руу дамжуулна.

## Тайлбар

- `/challenge/pwn` нь олон мөр гаралт үүсгэдэг ба тэдгээрийн зөвхөн **эхний 7 мөр** нь зөв "код" байна.
- `head -n 7` — stdin-ээс уншсан эхний 7 мөрийг л stdout руу гаргаж, үлдсэнийг нь хаяна.
- `/challenge/college` нь эдгээр 7 мөрийг stdin-ээсээ хүлээж авч шалгаад, зөв бол флагийг хэвлэнэ.
- Гурван программыг `|` пайпаар холбосноор нэг программын stdout нөгөөгийнх нь stdin болно.

## Solution

```console
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challenge/college
Congratulations, you piped the right codes!
pwn.college{o8ZPL1wnFrvWlNnBgji9sEaQ8u8.0lNxEzNxwyMwEzM2EzW}
```

## Flag

```
pwn.college{o8ZPL1wnFrvWlNnBgji9sEaQ8u8.0lNxEzNxwyMwEzM2EzW}
```
