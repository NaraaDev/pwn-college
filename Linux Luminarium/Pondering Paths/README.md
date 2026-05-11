# Pondering Paths

Linux дахь **зам (path)** ойлголтыг бүрэн эзэмшинэ — absolute, relative, home, root.

## Challenges

- [The root](./The%20root.md) — root (`/`) директор
- [Program and Absolute Path](./Program%20and%20Absolute%20Path.md) — absolute path-аар програм дуудах
- [Position Thy Self](./Position%20Thy%20Self.md) — `cd` ашиглан зөв байрлал руу шилжих
- [Position Elsewhere](./Positino%20Elsewhere.md) — олон төрлийн директор руу шилжих
- [Implicit Relative Paths](./Implicit%20Relative%20Paths.md) — `./` дутуу path
- [Implicit Relative Paths, from /](./Implicit%20Relative%20Paths%2C%20from%20Implicit%20Relative%20Paths%2C%20from%20.md) — `/` директораас relative
- [Explicit Relative Paths, from /](./Explicit%20Relative%20Pahs%2C%20from.md) — `./challenge/run` хэлбэр
- [Home Sweet Home](./Home%20Sweet%20Home.md) — `~` (`$HOME`) ашиглах

## Үндсэн ойлголт

| Path төрөл | Жишээ | Тайлбар |
|------------|-------|---------|
| Absolute | `/challenge/run` | `/` (root)-оос эхэлнэ. Хаанаас ч хамаагүй ажиллана. |
| Implicit relative | `challenge/run` | Одоогийн `pwd`-ээс эхэлнэ. |
| Explicit relative | `./challenge/run` | `.` = "одоогийн директор". |
| Parent | `..` | Дээд директор. `cd ..` |
| Home | `~` эсвэл `$HOME` | `/home/<user>` |
