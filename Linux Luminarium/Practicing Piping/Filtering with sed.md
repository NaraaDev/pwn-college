# Filtering With sed

> Module: **Linux Luminarium / Practicing Piping** · Challenge: `filtering-with-sed`

`sed`-ийн `s///g` орлуулах командыг ашиглан гаралт дахь хуурамч тэмдэгтүүдийг арилгаж, жинхэнэ флагийг гаргаж авна.

## Тайлбар

- `/challenge/run | sed "s/FAKEFLAG//g"` — challenge программын гаралтад холилдсон `FAKEFLAG` гэсэн бүх тохиолдлыг `sed`-ийн `s/pattern/replacement/g` командаар хоосон утгаар орлуулж (буюу устгаж) байна.
- `g` (global) флаг нь мөр бүрт олдсон **бүх** тохиолдлыг орлуулна, зөвхөн эхнийхийг биш.
- Үр дүнд нь `FAKEFLAG` холилдсон хэсгүүд арилж, цэвэр флаг л үлдэнэ.

## Solution

```console
hacker@piping~filtering-with-sed:~$ /challenge/run | sed "s/FAKEFLAG//g"
pwn.college{8Og6LbVOZQyBFUWvxlS2lGScLUE.01NxQTMywyMwEzM2EzW}
```

## Flag

```
pwn.college{8Og6LbVOZQyBFUWvxlS2lGScLUE.01NxQTMywyMwEzM2EzW}
```
