# Finding Files

> Module: **Comprehending Commands** · Challenge: `finding-files`

`find` командаар файлын системийг бүхэлд нь хайж, `flag` нэртэй файлыг олоод `cat`-аар уншиж flag авах сорилт.

## Тайлбар

| Команд | Тайлбар |
|--------|---------|
| `find / -name flag` | Үндсэн `/` директороос бүх дэд хавтсыг хайж, нэр нь `flag` болох бүх файлыг хэвлэнэ. Permission denied алдаанууд нормал — читах эрхгүй директорууд. |
| `cat <path>` | Олдсон замуудаас зөв (unших боломжтой) файлыг уншина. |

`find`-ийн `Permission denied` алдаа нь `/root`, `/proc` зэрэг системийн хамгаалалттай директоруудаас гардаг бөгөөд энэ нь хайлтад саад болохгүй — бусад замуудад хайлт үргэлжилнэ.

`/usr/share/doc/python3-idna/flag` нь унших боломжтой байв.

## Solution

```console
hacker@commands~finding-files:/$ find / -name flag
find: '/root': Permission denied
find: '/proc/1/task/1/fd': Permission denied
...
/usr/lib/python3/dist-packages/pwnlib/flag
/usr/share/doc/python3-idna/flag
...
hacker@commands~finding-files:/$ cat /usr/share/doc/python3-idna/flag
pwn.college{wq3lMnZZZBIaIY0Bl__1lmTYppg.QXyMDO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{wq3lMnZZZBIaIY0Bl__1lmTYppg.QXyMDO0wyMwEzM2EzW}
```
