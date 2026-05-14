# Help for Builtins

> Module: **Linux Luminarium / Digesting Documentation** · Challenge: `help-for-builtins`

Bash-ийн дотоод (builtin) командын `help` мэдээллийг ашиглан `challenge` builtin-ийн зөв нууц утгыг олж flag-ийг авах сорилт.

## Тайлбар

| Команд | Тайлбар |
|--------|---------|
| `help` | Bash-ийн бүх builtin командын жагсаалт. Жагсаалтад `challenge [--fortune] [--version] [--secret SECRET]` гэж байгааг анзаарна. |
| `help cd` | Тодорхой builtin-ийн дэлгэрэнгүй тайлбар. |
| `cd --help` | Builtin тус бүр `--help` сонголтыг дэмждэг. |
| `cat .challenge.so` | `--secret`-д өгөх зөв утгыг ELF доторх string-аас олж авна (`USM9Mzqt`). |
| `challenge --secret USM9Mzqt` | Зөв нууц утгыг өгч flag хүлээн авна. |

## Solution

```console
hacker@man~help-for-builtins:/challenge$ help
GNU bash, version 5.3.3(1)-release (x86_64-pc-linux-gnu)
These shell commands are defined internally. Type `help' to see this list.
...
challenge [--fortune] [--version] [--secret SECRET]
...

hacker@man~help-for-builtins:/challenge$ challenge --secret asdf
ERROR: incorrect argument to --secret. Read the help!

hacker@man~help-for-builtins:/challenge$ cat .challenge.so
... (ELF binary) ...
This builtin command will read you the flag, given the right arguments!
Options:
--fortune       display a fortune
--version       display the version
--secret VALUE  prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "USM9Mzqt".

hacker@man~help-for-builtins:/challenge$ challenge --secret USM9Mzqt
Correct! Here is your flag!
pwn.college{USM9MzqtUXxvRyk7SoY8hZBKal1.QX0ETO0wyMwEzM2EzW}
```

## Гол сургамж

Bash-ийн builtin командуудад `man` ажиллахгүй — оронд нь `help <name>` эсвэл `<name> --help` ашиглана. Зарим builtin-ийн help нь тусдаа `.so` файлд агуулагдаж, доторх string-ийг шууд уншиж нууц утгыг олж болно.

## Flag

```
pwn.college{USM9MzqtUXxvRyk7SoY8hZBKal1.QX0ETO0wyMwEzM2EzW}
```
