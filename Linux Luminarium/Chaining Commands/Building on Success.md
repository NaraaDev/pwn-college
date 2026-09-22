# Building on Success

> Module: **Linux Luminarium / Chaining Commands** · Challenge: `building-on-success`

`&&`-ээр `/challenge/first-success` амжилттай (exit code `0`) дууссан үед л `/challenge/second`-ийг ажиллуулж флаг авна.

## Тайлбар

- `command1 && command2` — "AND" оператор: command1 **амжилттай** (exit code `0`) дууссан үед л command2 ажиллана. Эхнийх бүтэлгүйтвэл (0-ээс ялгаатай код) хоёр дахь нь огт ажиллахгүй.
- Processes and Jobs модульд үзсэн exit code-ыг энд ашиглаж байна: Linux-д `0` = амжилт, бусад = алдаа. Жишээ нь `touch /file && echo ...` — `hacker`-т `/`-д бичих эрх байхгүй тул `touch` бүтэлгүйтэж, `echo` ажиллахгүй.
- `/challenge/first-success` ба `/challenge/second`-ийг тус тусад нь ажиллуулахад флаг өгөхгүй; `&&`-ээр залгасан үед л хоёр дахь программ chained гэдгийг таньж флагийг хэвлэнэ.

## Solution

```console
hacker@chaining~building-on-success:~$ /challenge/first-success && /challenge/second
Nice chaining! Flag: pwn.college{ETcASrM3CrdsYiSr2cPejtxykwd.0lM0MDOxwyMwEzM2EzW}
```

## Flag

```
pwn.college{ETcASrM3CrdsYiSr2cPejtxykwd.0lM0MDOxwyMwEzM2EzW}
```
