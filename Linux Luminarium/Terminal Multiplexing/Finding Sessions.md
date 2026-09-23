# Finding Sessions

> Module: **Linux Luminarium / Terminal Multiplexing** · Challenge: `finding-sessions`

`screen -ls`-ээр гурван session-ийг жагсааж, `screen -r <name>`-ээр нэг бүрчлэн attach хийж флагтайг нь олно.

## Тайлбар

- Олон session байх үед `screen -ls` нь бүгдийг `<PID>.<name> (Detached)` хэлбэрээр жагсаана (socket-ууд нь `/run/screen/S-hacker`-д).
- Тодорхой session руу attach хийхдээ нэр эсвэл PID-ийг `screen -r`-д аргумент болгон өгнө: `screen -r goodwork`.
- Гурван session-ий нэг нь флагтай, хоёр нь decoy. Дараагийнхыг шалгахаас өмнө `Ctrl-A d`-ээр detach хийх ёстой.
- Хуулсан хэсэгт session-уудыг шалгасан алхмууд үлдээгүй — зөвхөн флагтай session дотор хэвлэгдсэн мөр байна.

## Solution

```console
pwn.college{IpT2dx_0lqjFS_2pzsl4aWWKqKX.01N4IDOxwyMwEzM2EzW}
```

## Flag

```
pwn.college{IpT2dx_0lqjFS_2pzsl4aWWKqKX.01N4IDOxwyMwEzM2EzW}
```
