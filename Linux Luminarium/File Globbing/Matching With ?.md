# Matching With ?

> Module: **Linux Luminarium / File Globbing** · Challenge: `matching-with-`

`?` glob тэмдэгийг ашиглан `/challenge`-руу `cd` хийж, `./run`-ийг ажиллуулна.

## Тайлбар

| Команд | Тайлбар |
|--------|---------|
| `?` | Яг **нэг** дурын тэмдэгтийг тааруулна (`*`-тай адил биш — `*` нь олон тэмдэгтийг тааруулдаг). |
| `cd /?ha??enge` | `/challenge` нэрийг яг 9 тэмдэгтээр тааруулна: `c`→`?`, `h`→`h`, `a`→`a`, `l`→`?`, `l`→`?`, `e`→`e`, `n`→`n`, `g`→`g`, `e`→`e`. |
| `./run` | `/challenge` директор дотроос ажиллуулж flag-аа авна. |

## Solution

```console
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ ls
Dockerfile run
hacker@globbing~matching-with-:/challenge$ ./run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{AlQ6VAKhQd78ze5U-ApdsXK8_up.QXyIDO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{AlQ6VAKhQd78ze5U-ApdsXK8_up.QXyIDO0wyMwEzM2EzW}
```
