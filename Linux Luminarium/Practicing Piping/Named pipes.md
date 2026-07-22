# Named Pipes

> Module: **Linux Luminarium / Practicing Piping** · Challenge: `named-pipes`

`mkfifo`-аар нэрлэсэн пайп (FIFO) үүсгэж, ердийн пайп (`|`) ашиглахгүйгээр хоёр тусдаа команд хооронд өгөгдөл дамжуулна.

## Тайлбар

- Эхний оролдлого: `/challenge/run > /tmp/flag_fifo`-г ажиллуулахаас өмнө уншиж эхлээгүй тул FIFO нь **блоклогдож** (block), хоёр талын (унших/бичих) нээгдэхийг хүлээсээр зогссон. Тиймээс `^C`-ээр таслах шаардлагатай болсон.
- FIFO дээрх үйлдлүүд унших ба бичих тал хоёул нээгдэх хүртэл блоклогддог тул `cat /tmp/flag_fifo`-г эхлээд **дэвсгэр процесс** (`&`) болгон ажиллуулж, дараа нь `/challenge/run > /tmp/flag_fifo`-г ажиллуулснаар хоёр тал зэрэг нээгдэж, өгөгдөл дамжсан.
- Named pipe нь энгийн `|` пайптай адил зан төлөвтэй боловч файл систем дээр нэр (path)-тэй байдгаараа ялгаатай — тусдаа терминал/процессуудаас холбогдох боломжтой.

## Solution

```console
hacker@piping~named-pipes:~$ rm -f /tmp/flag_fifo
mkfifo /tmp/flag_fifo
cat /tmp/flag_fifo
/challenge/run > /tmp/flag_fifo
^C
hacker@piping~named-pipes:~$ rm -f /tmp/flag_fifo
mkfifo /tmp/flag_fifo
cat /tmp/flag_fifo &
/challenge/run > /tmp/flag_fifo
[1] 135
You're successfully redirecting /challenge/run to a FIFO at /tmp/flag_fifo!
Bash will now try to open the FIFO for writing, to pass it as the stdout of
/challenge/run. Recall that operations on FIFOs will *block* until both the
read side and the write side is open, so /challenge/run will not actually be
launched until you start reading from the FIFO!
You've correctly redirected /challenge/run's stdout to a FIFO at
/tmp/flag_fifo! Here is your flag:
pwn.college{gQAWjaa631qGQ7h-lUDoNw9MJxc.01MzMDOxwyMwEzM2EzW}
[1]+  Done                       cat /tmp/flag_fifo
```

## Flag

```
pwn.college{gQAWjaa631qGQ7h-lUDoNw9MJxc.01MzMDOxwyMwEzM2EzW}
```
