# Switching Windows

> Module: **Linux Luminarium / Terminal Multiplexing** · Challenge: `switching-windows`

`screen -r`-ээр бэлдсэн session-д attach хийж, window 0 руу шилжиж флаг авна.

## Тайлбар

- Нэг screen session дотор browser-ийн tab шиг олон **window** байж болно. Бүх shortcut `Ctrl-A`-аар эхэлнэ:
  - `Ctrl-A c` — шинэ window үүсгэх
  - `Ctrl-A n` / `Ctrl-A p` — дараагийн / өмнөх window
  - `Ctrl-A 0` … `Ctrl-A 9` — дугаартай window руу шууд
  - `Ctrl-A "` — бүх window-ийн сонголтын цэс
- Session-д window 0 (флагтай) ба window 1 (мэндчилгээтэй) гэсэн хоёр window бий.
- Window 0 дотор challenge `cat <<MSG ... MSG` (heredoc) командаар флагийг хэвлэсэн байна; `>` нь heredoc-ийн үргэлжлэлийн prompt.
- Дараалал: `screen -r` → `Ctrl-A 0` (эсвэл `Ctrl-A n`/`p`).
- Хуулахад `>` мөрүүд markdown quote болж эвдэрсэн байсныг terminal дээр харагдах хэлбэрт нь буцаав.

## Solution

```console
hacker@terminal-multiplexing~switching-windows:~$ cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{scj9aCCi6stcjypULldKnHWwFKb.0FO4IDOxwyMwEzM2EzW}
> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{scj9aCCi6stcjypULldKnHWwFKb.0FO4IDOxwyMwEzM2EzW}
hacker@terminal-multiplexing~switching-windows:~$
```

## Flag

```
pwn.college{scj9aCCi6stcjypULldKnHWwFKb.0FO4IDOxwyMwEzM2EzW}
```
