# Detaching and Attaching

> Module: **Linux Luminarium / Terminal Multiplexing** · Challenge: `detaching-and-attaching`

`screen` session-оос `Ctrl-A d`-ээр detach хийж, `/challenge/run`-ийг ажиллуулаад `screen -r`-ээр буцаж attach хийхэд флаг session дотор хүлээж байна.

## Тайлбар

- Remote холболт тасарсан ч screen session ардаа ажилласаар байдаг тул дараа нь буцаж холбогдож болно. Үүнийг зориуд хийхийг **detach** гэнэ.
- Detach: `Ctrl-A`-г дараад суллаж, дараа нь `d` → `[detached from ...]`. `Ctrl-A` нь screen-ийн бүх shortcut-ийн prefix (activation key).
- Reattach: `screen -r`.
- `/challenge/run` нь detach хийсэн session руу флаг хэвлэх `echo` командыг нууцаар илгээдэг — тиймээс attach хийхэд session дотор `echo Yes! Flag is: ...` мөр харагдана.
- Дараалал: `screen` → `Ctrl-A d` → `/challenge/run` → `screen -r`.

## Solution

```console
hacker@terminal-multiplexing~detaching-and-attaching:~$
hacker@terminal-multiplexing~detaching-and-attaching:~$ echo Yes! Flag is: pwn.college{kLHLt2B1iXLLJeiY-E2BPivbeqi.0lN4IDOxwyMwEzM2EzW}
Yes! Flag is: pwn.college{kLHLt2B1iXLLJeiY-E2BPivbeqi.0lN4IDOxwyMwEzM2EzW}
hacker@terminal-multiplexing~detaching-and-attaching:~$
```

## Flag

```
pwn.college{kLHLt2B1iXLLJeiY-E2BPivbeqi.0lN4IDOxwyMwEzM2EzW}
```
