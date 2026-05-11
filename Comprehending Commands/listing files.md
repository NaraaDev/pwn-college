# Listing Files

> Module: **Comprehending Commands** · Challenge: `listing-files`

`ls` ашиглан директор доторх файлуудыг олж харах. Challenge нь `run`-ыг санамсаргүй нэр болгож хувиргасан.

## Тайлбар

- `ls` — одоогийн директор доторх файлууд.
- `ls /challenge/` — `/challenge` доторх файлууд.
- `ls -l` — нарийвчилсан мэдээлэл (эрх, эзэмшигч, хэмжээ, огноо).
- `ls -a` — нуугдсан (`.`-аар эхэлсэн) файлуудыг ч харуулах.
- Энэ challenge: `run` гэсэн нэр нь `2822-renamed-run-19136` болж өөрчлөгдсөн. `ls`-ээр олж буй нэрээр дуудна: `/challenge/2822-renamed-run-19136`.

```bash
ls -la /challenge
```

## Solution

```console
hacker@commands~listing-files:~$ ls /challenge/
2822-renamed-run-19136 Dockerfile
hacker@commands~listing-files:~$ /challenge/2822-renamed-run-19136
Yahaha, you found me! Here is your flag:
pwn.college{oud8rhKVe3HmSunczrfN2VfED9a.QX4IDO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{oud8rhKVe3HmSunczrfN2VfED9a.QX4IDO0wyMwEzM2EzW}
```
