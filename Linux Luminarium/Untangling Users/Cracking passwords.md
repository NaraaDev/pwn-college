# Cracking passwords

> Module: **Linux Luminarium / Untangling Users** · Challenge: `cracking-passwords`

Задарсан `/etc/shadow`-оос John the Ripper-ээр `zardus`-ийн нууц үгийг тайлж, `su zardus` хийгээд `/challenge/run`-ийг ажиллуулна.

## Тайлбар

- Хэрэглэгчдийн нууц үг өмнө нь `/etc/passwd`-д байсан ч тэр файл бүх хүнд уншигддаг тул нууц үгсийг зөвхөн root уншдаг `/etc/shadow`-руу зөөсөн.
- `/etc/shadow` мөр бүр `:`-ээр тусгаарлагдана: 1-р талбар — нэр, 2-р талбар — нууц үгийн **хэш**. `*`/`!` нь password login идэвхгүй, хоосон талбар нь нууц үггүй (misconfiguration), `$6$...` нь SHA-512-оор нэг талын хэшлэсэн утга.
- `su`-д нууц үг оруулахад тэр хэшлээд хадгалсан утгатай харьцуулдаг. Хэш байхад **crack** хийж болно — backup зэргээс `/etc/shadow` алдагдвал энэ эрсдэлтэй.
- **John the Ripper** (`john`) нь хэшийг dictionary/brute-force-оор тайлдаг: `john /challenge/shadow-leak` → `password1337 (zardus)`. Хэдэн минут авч болно.
- Тайлсан нууц үгээр `su zardus` хийгээд `/challenge/run`-ийг ажиллуулж флаг авна.

## Solution

```console
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Will run 32 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
password1337 (zardus)
1g 0:00:00:22 3/3 0.04528g/s 10509p/s 10509c/s 10509C/s lykys..lank
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ su zardus
Password:
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
pwn.college{sLG1A2bHOF9SMScPFGbBC348YXn.QX3UDN1wyMwEzM2EzW}
```

## Flag

```
pwn.college{sLG1A2bHOF9SMScPFGbBC348YXn.QX3UDN1wyMwEzM2EzW}
```
