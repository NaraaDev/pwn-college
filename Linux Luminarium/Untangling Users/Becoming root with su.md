# Becoming root with su

> Module: **Linux Luminarium / Untangling Users** · Challenge: `becoming-root-with-su`

`su`-гээр root болж (root-ийн нууц үг `hack-the-planet`), `/challenge/run`-ийг ажиллуулаад `/flag`-ийг унших.

## Тайлбар

- `su` (substitute user) нь **SUID** binary — `ls -l /usr/bin/su`-д `-rwsr-xr-x root root` (эзэн дээрх `s` бит). Тиймээс аль ч хэрэглэгч ажиллуулахад root эрхээр ажиллана.
- Гэхдээ `su` эрх өгөхийн өмнө **root-ийн нууц үгийг** шалгадаг. Орчин үеийн системд root password ихэвчлэн байдаггүй тул `su`-г элдэвлэхэд хэрэглэдэггүй болсон — энэ challenge л онцгойлж root password-той (`hack-the-planet`).
- Root болсны дараа `/challenge/run` баталгаажуулаад, `cat /flag`-ээр флагийг шууд уншина.
- Home директор дахь `myflag`, `the-flag`, `output.txt` зэрэг нь **өмнөх level-үүдийн** үлдэгдэл файлууд — энэ challenge-ийн флаг биш.

## Solution

```console
hacker@users~becoming-root-with-su:~$ su
Password:
root@users~becoming-root-with-su:/home/hacker# /challenge/run
Congratulations, you have become root!
You can now read the flag yourself. Run: cat /flag
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{sdUW7Eyhs555Y32apae6S13ILP-.QX1UDN1wyMwEzM2EzW}
root@users~becoming-root-with-su:/home/hacker#
```

## Flag

```
pwn.college{sdUW7Eyhs555Y32apae6S13ILP-.QX1UDN1wyMwEzM2EzW}
```
