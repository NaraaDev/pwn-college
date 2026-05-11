# An Epic FileSystem Quest

> Module: **Comprehending Commands** · Challenge: `an-epic-filesystem-quest`

Олон шатлал файлын системийг туулж буй сорилт. Шат бүрд clue файл байх ба дараагийн зам руугаа ийш тийш чиглүүлнэ. `cd`, `ls`, `ls -a`, `cat` коммандуудыг хослуулан хэрэглэнэ.

## Тайлбар

Clue 4 төрөл:

| Clue type | Зөв арга |
|-----------|----------|
| **delayed** | Заасан директор руу `cd` хийсний дараа л унших боломжтой. |
| **hidden** | Файлын нэр `.`-аар эхэлсэн. `ls -a` ашиглаж олно. |
| **trapped** | `cd` хийвэл файл устана. **Гадуураас** `cat /abs/path/...` гэж шууд унш. |
| **normal** | `ls` → `cat <file>` |

Clue гинж:

1. `/TRACE` → дараагийн clue `/usr/lib/x86_64-linux-gnu/perl/5.38.2/auto/NDBM_File/` (delayed)
2. `TEASER` → `/usr/lib/python3/dist-packages/pip/_internal/metadata/__pycache__/` (hidden — `.SECRET`)
3. `.SECRET` → `/usr/lib/python3/dist-packages/pwnlib/data/elf/relro/__pycache__/` (trapped — `NUGGET-TRAPPED`)
4. `NUGGET-TRAPPED` → `/usr/include/linux/nfsd/HINT`
5. `HINT` → `/usr/share/doc/sudo/NOTE`
6. `NOTE` → `/usr/share/python3/dist/README`
7. `README` → `/usr/lib/python3/dist-packages/plumbum/cli/i18n/de/LC_MESSAGES/` (trapped — `ALERT-TRAPPED`)
8. `ALERT-TRAPPED` → `/usr/share/perl/5.38.2/IO/Socket/` (trapped — `DISPATCH-TRAPPED`)
9. `DISPATCH-TRAPPED` → 🚩 **flag**

## Solution (товчилсон)

```console
hacker@an-epic-filesystem-quest:/$ cat /TRACE
# → cd /usr/lib/x86_64-linux-gnu/perl/5.38.2/auto/NDBM_File
hacker@...:.../NDBM_File$ cat TEASER
# → cd /usr/lib/python3/dist-packages/pip/_internal/metadata/__pycache__
hacker@...:.../__pycache__$ ls -a    # hidden clue
hacker@...:.../__pycache__$ cat .SECRET
# → trapped: cat-аар гадуурх unath
hacker@...:.../__pycache__$ cat /usr/lib/python3/dist-packages/pwnlib/data/elf/relro/__pycache__/NUGGET-TRAPPED
# → /usr/include/linux/nfsd
hacker@...:.../nfsd$ cat HINT
# → /usr/share/doc/sudo
hacker@...:.../sudo$ cat NOTE
# → /usr/share/python3/dist
hacker@...:.../dist$ cat README
# → trapped clue
hacker@...:.../dist$ cat /usr/lib/python3/dist-packages/plumbum/cli/i18n/de/LC_MESSAGES/ALERT-TRAPPED
# → trapped clue
hacker@...:.../dist$ cat /usr/share/perl/5.38.2/IO/Socket/DISPATCH-TRAPPED
CONGRATULATIONS! ...
pwn.college{8g8NwwdHikkhJIxrSm2E-hR4YEN.QX5IDO0wyMwEzM2EzW}
```

## Гол сургамж

- **Trapped clue**: `cd` хийхгүйгээр `cat /full/abs/path/file` гэж шууд unath.
- **Hidden clue**: `ls -a` ашиглах. `.`-аар эхэлсэн файл харагдана.
- **Delayed clue**: заавал `cd` хийсний дараа агуулга бүрэн уншигдана.

## Flag

```
pwn.college{8g8NwwdHikkhJIxrSm2E-hR4YEN.QX5IDO0wyMwEzM2EzW}
```
