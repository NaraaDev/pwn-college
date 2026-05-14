# Matching With *

> Module: **Linux Luminarium / File Globbing** · Challenge: `matching-with-`

`*` glob тэмдэгийг ашиглан `/challenge`-руу 4 хүртэлх тэмдэгтийн хязгаарт багтаан `cd` хийж, `./run`-ийг ажиллуулна.

## Тайлбар

| Команд | Тайлбар |
|--------|---------|
| `cd /challenge` | 10 тэмдэгт — `more than 4 characters. Disallowed!` алдаа. |
| `cd /ch*` | `*` нь shell glob тэмдэг — `/ch`-аар эхэлсэн нэрийг тааруулна. 4 тэмдэгт учир зөвшөөрөгдөнө, `/challenge`-руу шилждэг. |
| `./run` | `/challenge` дотроос ажиллуулж flag-аа авна. |

## Solution

```console
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ ls
Dockerfile run
hacker@globbing~matching-with-:/challenge$ ./run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{Y9leUxuYQrYkRlVn0wqfLfIJc4n.QXxIDO0wyMwEzM2EzW}
```
