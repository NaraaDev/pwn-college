# Exclusionary Globbing

> Module: **Linux Luminarium / File Globbing** · Challenge: `exclusionary-globbing`

`[!...]` glob ашиглан тодорхой угтвартай **биш** файлуудыг л challenge-ийн программд дамжуулна.

## Тайлбар

- `[!pwn]` — эхний тэмдэгт нь `p`, `w`, эсвэл `n` **биш** байх ёстой (bracket expression-ийн `!` нь тухайн жагсаалтыг үгүйсгэнэ).
- `*` — дараа нь юу ч ирж болно.
- Ийнхүү `[!pwn]*` нь `p`, `w`, `n`-ээр эхэлдэггүй бүх файлыг тааруулна.

```bash
/challenge/run [!pwn]*
```

## Solution

```console
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{c0OFbuVov0TJ2vH8Qq2tinwTY-X.QX2IDO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{c0OFbuVov0TJ2vH8Qq2tinwTY-X.QX2IDO0wyMwEzM2EzW}
```
