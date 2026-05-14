# Helpful Programs

> Module: **Linux Luminarium / Digesting Documentation** · Challenge: `helpful-programs`

Программын `-h` / `--help` сонголтоор тусламжийг уншиж, шаардлагатай аргументуудыг олж ашиглан flag-ийг авах сорилт.

## Тайлбар

| Команд | Тайлбар |
|--------|---------|
| `./challenge` | Аргумент дутуу — `No options specified.` гэж буцаана. |
| `./challenge -h` (эсвэл `--help`) | Программын help-ийг хэвлэнэ. `-g` болон `-p` гэсэн хоёр гол сонголтыг олж харна. |
| `./challenge -p` | `-g`-д өгөх зөв нууц утгыг хэвлэнэ (`866`). |
| `./challenge -g 866` | Зөв утгыг өгч flag-ийг авна. |

Help-ээс олсон сонголтууд:
```
-g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                      get the flag, if given the correct value
-p, --print-value     print the value that will cause the -g option to give you the flag
```

## Solution

```console
hacker@man~helpful-programs:/challenge$ ./challenge -h
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

options:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag

hacker@man~helpful-programs:/challenge$ ./challenge -p
The secret value is: 866

hacker@man~helpful-programs:/challenge$ ./challenge -g 866
Correct usage! Your flag: pwn.college{866mVPTQxJeC5UA5MXOEEiAYFvu.QX3IDO0wyMwEzM2EzW}
```

## Гол сургамж

Шинэ программ ажиллуулахдаа эхлээд `-h` / `--help` ашиглан түүний боломжуудыг танилцана. Help-ээс олсон сонголтуудыг зөв дараалалд ашиглан асуудлыг шийднэ.

## Flag

```
pwn.college{866mVPTQxJeC5UA5MXOEEiAYFvu.QX3IDO0wyMwEzM2EzW}
```
