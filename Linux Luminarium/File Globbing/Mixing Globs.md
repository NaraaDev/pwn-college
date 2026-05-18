# Mixing Globs

> Module: **Linux Luminarium / File Globbing** · Challenge: `mixing-globs`

`*` болон `[]` glob тэмдэгүүдийг хольж ашиглан тодорхой файлуудыг л challenge-ийн программд дамжуулна.

## Тайлбар

- Зорилго: `challenging`, `educational`, `pwning` гурван файлыг л тааруулах.
- Эхний оролдлого `*[*n]?` буруу: `*` — escape хийгээгүй ч `[*n]` дотор `*` нь литерал тэмдэгт болохоор хэт олон файл (amazing, kind, radiant…) таарсан.
- Зөв шийдэл `[cep]\*`:
  - `[cep]` — эхний тэмдэгт нь `c`, `e`, эсвэл `p` байх ёстой → `challenging` (`c`), `educational` (`e`), `pwning` (`p`)-г тааруулна.
  - `\*` — escape хийсэн `*` нь хоёр дахь glob `*` бөгөөд дараагаар нь юу ч ирж болно.

```bash
../run [cep]*
```

## Solution

```console
hacker@globbing~mixing-globs:/challenge/files$ ../run *[*n]?
Your expansion did not expand to the requested files (challenging, educational,
pwning). Instead, it expanded to:
amazing challenging kind laughing pwning radiant thrilling uplifting
hacker@globbing~mixing-globs:/challenge/files$ ../run [cep]\*
You got it! Here is your flag!
```

## Flag

> Бодоогүй / тэмдэглэлгүй.
