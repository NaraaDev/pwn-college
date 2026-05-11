# Explicit Relative Paths, from /

> Module: **Linux Luminarium / Pondering Paths** · Challenge: `explicit-relative-paths-from-/`

`/` директораас `./challenge/run` гэж **explicit relative path** (`./`-тэй) ашиглан дуудна.

## Тайлбар

- `cd ..` — нэг шат дээш гарах. `~` → `/home` → `/`.
- Энэ challenge нь зөвхөн `.`-аар эхэлсэн relative path хүлээж авна.
  - `challenge/run` — буруу (`.` байхгүй).
  - `./challenge/run` — зөв.
- Зөв нөхцөл: **`/` директорт байж байгаад** `./challenge/run` гэж дуудах.

## Solution

```console
hacker@paths~explicit-relative-paths-from-:/$ challenge/run
Incorrect...
This challenge must be called with a relative path that explicitly starts with a `.`!
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{wDRcP_T0Toyk-XK98Vn3t8aX4yu.QXwUTN0wyMwEzM2EzW}
```

## Flag

```
pwn.college{wDRcP_T0Toyk-XK98Vn3t8aX4yu.QXwUTN0wyMwEzM2EzW}
```
