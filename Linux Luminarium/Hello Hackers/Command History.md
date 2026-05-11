# Command History

> Module: **Linux Luminarium / Hello Hackers** · Challenge: `command-history`

Bash коммандуудын **түүхийг** хадгалдаг. Өмнөх коммандуудыг дахин дуудаж болно.

## Тайлбар

- `history` — өмнө бичсэн коммандуудын дугаарласан жагсаалт.
- **↑ / ↓ сум** — өмнөх / дараагийн комманд руу шилжих.
- **`Ctrl+R`** — түүхээс **урвуу хайлт** (reverse-i-search). Бичсэн утгад тохирох сүүлийн коммандыг гаргана.
- **`!<number>`** — тухайн дугаартай коммандыг дахин ажиллуулна. Ж.нь `!42`.
- **`!!`** — хамгийн сүүлд ажиллуулсан коммандыг давтана.

```bash
history          # бүх түүх
history | tail   # сүүлийн 10
!!               # сүүлийн коммандыг дахин ажиллуулах
```

## Solution

```console
hacker@hello~command-history:~$
Connected!
hacker@hello~command-history:~$ the flag is pwn.college{QUIvuNH3X5nTMS-wauholwVMu-q.0lNzEzNxwyMwEzM2EzW}
```

## Flag

```
pwn.college{QUIvuNH3X5nTMS-wauholwVMu-q.0lNzEzNxwyMwEzM2EzW}
```
