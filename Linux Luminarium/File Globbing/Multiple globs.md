# Multiple Globs

> Module: **Linux Luminarium / File Globbing** · Challenge: `multiple-globs`

Нэг команд дотор олон glob ашиглан тодорхой набор файлуудыг л өргөтгөж challenge-ийн программд дамжуулна.

## Тайлбар

- Энэ challenge нь `happy`, `optimistic`, `pwning`, `splendid`, `uplifting` файлуудыг л өргөтгөхийг хүсдэг.
- `*` ганцаараа бол **бүх** файлыг тааруулна — хэт өргөн.
- `*p\*` гэдэг нь:
  - Эхний `*` — өмнө нь юу ч байж болно.
  - `p` — заавал `p` тэмдэгт байх ёстой.
  - `\*` — backslash-аар escape хийсэн `*`, өөрөөр хэлбэл хоёр дахь `*` нь литерал бус glob хэвээрээ үлдэж дараах юу ч таарах боломжтой.
- Үр дүнд `p` тэмдэгт **дотроо** агуулсан үгс л таарна: `happy`, `optimistic`, `pwning`, `splendid`, `uplifting`.

```bash
../run *p*
```

## Solution

```console
hacker@globbing~multiple-globs:/challenge/files$ ls
amazing challenging educational great incredible kind magical optimistic queenly splendid uplifting wonderful youthful
beautiful delightful fantastic happy jovial laughing nice pwning radiant thrilling victorious xenial zesty
hacker@globbing~multiple-globs:/challenge/files$ ../run *
Your expansion did not expand to the requested files (happy optimistic pwning
splendid uplifting).
Instead, it expanded to:
amazing beautiful challenging delightful educational fantastic great happy incredible jovial kind laughing magical nice optimistic pwning queenly radiant splendid thrilling uplifting victorious wonderful xenial youthful zesty
hacker@globbing~multiple-globs:/challenge/files$ ../run *p\*
You got it! Here is your flag!
pwn.college{UAI0PvsKGDbRJvwBh6q1ejwApbh.0lM3kjNxwyMwEzM2EzW}
```

## Flag

```
pwn.college{UAI0PvsKGDbRJvwBh6q1ejwApbh.0lM3kjNxwyMwEzM2EzW}
```
