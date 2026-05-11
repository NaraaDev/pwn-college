# pwn.college Writeups

[pwn.college](https://pwn.college) сорилуудыг бодсон тэмдэглэлүүд. Challenge бүрд terminal session болон олж авсан flag-ийг хадгалсан.

## Modules

| # | Module | Challenges |
|---|--------|-----------|
| 1 | [Start Here](./Start-Here) | 11 |
| 2 | [Linux Luminarium — Hello Hackers](./Linux%20Luminarium/Hello%20Hackers) | 3 |
| 3 | [Linux Luminarium — Pondering Paths](./Linux%20Luminarium/Pondering%20Paths) | 8 |
| 4 | [Comprehending Commands](./Comprehending%20Commands) | 11 |

## Format

`module/challenge-name.md` файл бүр дараах бүтэцтэй:

- **Title** — challenge нэр
- **Solution** — terminal session (`console` code-block)
- **Flag** — `pwn.college{...}` формат

## Tools

```bash
# Reading
cat <file>            # файл хэвлэх
ls /path              # директор үзэх
grep PATTERN file     # хайлт

# Navigation
cd /path              # директор сольх
pwd                   # одоогийн зам

# File ops
touch file            # шинэ файл
cp src dst            # хуулах
mv src dst            # шилжүүлэх
rm file               # устгах
```
