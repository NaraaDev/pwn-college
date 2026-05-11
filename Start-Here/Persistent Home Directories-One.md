# Persistent Home Directories

> Module: **Start Here** · Challenge: `persistent-home-directories`

Challenge орчин дахин асахад `/home/hacker` доорх файлууд **хадгалагдсан хэвээр** үлдэхийг харуулна. Бусад зам (`/tmp`, `/challenge`) дахин эхлэхэд цэвэрлэгддэг.

## Тайлбар

- **Home directory** — хэрэглэгчийн хувийн директор (`~` = `/home/hacker`).
- pwn.college платформ home директорыг volume-аар хадгалдаг — challenge restart хийсэн ч файл алга болохгүй.
- Challenge хооронд өөрийн скрипт, тэмдэглэлээ хадгалахад тохиромжтой газар.

```bash
echo "test" > ~/note.txt   # restart хийсэн ч үлдэнэ
ls ~                       # home доторхыг харах
```

## Flag

```
pwn.college{IFUOsNq0nYCxzwl4n_rLx4ZiPI6.QXxMzNzwyMwEzM2EzW}
```
