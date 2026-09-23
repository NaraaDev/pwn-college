# Launching Screen

> Module: **Linux Luminarium / Terminal Multiplexing** · Challenge: `launching-screen`

`screen`-ийг ажиллуулж screen session дотор ороход л флаг хэвлэгдэнэ.

## Тайлбар

- `screen` нь терминал дотор виртуал терминал (session) үүсгэдэг программ — browser-ийн tab шиг олон командын мөрийг нэг терминалд хадгална.
- Session дотор энгийн терминалаас ялгаагүй харагдах ч detach, олон window зэрэг нэмэлт боломжтой (дараагийн level-үүдэд).
- Энэ challenge-д `screen`-ийг эхлүүлэхэд л флаг автоматаар хэвлэгдэхээр тохируулсан. Доорх гаралт нь screen session-ий дотор талаас хуулагдсан тул `screen` командын мөр харагдахгүй.
- Session-оос гарахдаа `exit` эсвэл `Ctrl-D` — screen хаагдаж анхны shell рүү буцна.

## Solution

```console
Congratulations! You're inside a screen session!
Here's your flag:
pwn.college{MJl0yiu2OPr-Y2H12SZ2ozRVjDa.0VN4IDOxwyMwEzM2EzW}
hacker@terminal-multiplexing~launching-screen:~$
```

## Flag

```
pwn.college{MJl0yiu2OPr-Y2H12SZ2ozRVjDa.0VN4IDOxwyMwEzM2EzW}
```
