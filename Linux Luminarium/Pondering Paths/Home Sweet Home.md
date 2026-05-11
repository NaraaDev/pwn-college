# Home Sweet Home

> Module: **Linux Luminarium / Pondering Paths** · Challenge: `home-sweet-home`

`~` (tilde) тэмдэг bash-д хэрэглэгчийн **home** директор гэж тайлбарлагдана. Энэ challenge home доорх замыг богино хэлбэрээр өгөхийг шалгана.

## Тайлбар

- `~` → `/home/hacker` (одоогийн хэрэглэгчийн home).
- `~/a` → `/home/hacker/a`.
- Challenge шаардлага:
  - **Absolute path** өгөх (`/`-оос эхлэх).
  - Path нь **3 тэмдэгтээс илүүгүй** урт байх. Тийм учир `/home/hacker/a` (12 тэмдэгт) хүлээж авахгүй ч `~/a` (3 тэмдэгт) хүлээж авна — `~` нь shell-ээр expand хийгдсэний дараа absolute зам болсон.
- `cat` директорыг унших боломжгүй — зөвхөн файлд.

## Solution

```console
hacker@paths~home-sweet-home:~$ /challenge/run
You must provide an argument to /challenge/run when you invoke it!
hacker@paths~home-sweet-home:~$ /challenge/run home/hacker
The argument you provided must not have been longer than 3 characters!
hacker@paths~home-sweet-home:~$ /challenge/run /home/hacker
The argument you provided must not have been longer than 3 characters!
hacker@paths~home-sweet-home:~$ /challenge/run run
The argument you provided is not an absolute path!
hacker@paths~home-sweet-home:~$ /challenge/run ~/a
Writing the file to /home/hacker/a!
... and reading it back to you:
pwn.college{I1naLyMiowKNcWjclWhqB6-5XVJ.QXzMDO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{I1naLyMiowKNcWjclWhqB6-5XVJ.QXzMDO0wyMwEzM2EzW}
```
