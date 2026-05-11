# cat: not the pet, but the command!

> Module: **Comprehending Commands** · Challenge: `cat-not-the-pet-but-the-command`

`cat` — концат (concatenate)-ын товчлол. Зүгээр л файлын агуулгыг **стандарт гаралт** руу хэвлэх комманд.

## Тайлбар

- `cat <file>` — файлын агуулгыг хэвлэнэ.
- Олон файл өгвөл нэг нэгийнхээ араар залгуулна (concatenate).
- Энэ challenge-д home директор дотор `flag` нэртэй файл байрлуулсан байна. `cat flag` гэвэл агуулга нь гарна.

```bash
cat flag                  # одоогийн директор доторх flag
cat /tmp/x /tmp/y > z     # хоёр файлын агуулгыг нэгтгэх
```

## Solution

```console
hacker@commands~cat-not-the-pet-but-the-command:~$ ls
Desktop a flag leap rsa rsa.pub
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{ImZZX3ivTj4GvjXGR0TsTmW4rqD.QXxcTN0wyMwEzM2EzW}
```

## Flag

```
pwn.college{ImZZX3ivTj4GvjXGR0TsTmW4rqD.QXxcTN0wyMwEzM2EzW}
```
