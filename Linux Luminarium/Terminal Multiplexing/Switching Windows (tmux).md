# Switching Windows (tmux)

> Module: **Linux Luminarium / Terminal Multiplexing** · Challenge: `switching-windows-tmux`

tmux session-д attach хийж, `Ctrl-B 0`-ээр window 0 руу шилжиж флаг авна.

## Тайлбар

- tmux-ийн window-ууд screen-тэй ижил санаатай, зөвхөн prefix нь `Ctrl-B`:
  - `Ctrl-B c` — шинэ window үүсгэх
  - `Ctrl-B n` / `Ctrl-B p` — дараагийн / өмнөх window
  - `Ctrl-B 0` … `Ctrl-B 9` — дугаартай window руу шууд
  - `Ctrl-B w` — window picker
- Доод status bar: `[0] 0:bash* 1:bash` — `*` нь одоогийн window, нэр нь тухайн window-д ажиллаж буй процесс.
- Session-д window 0 (флагтай) ба window 1 (мэндчилгээтэй) гэсэн хоёр window бий.
- Дараалал: `tmux a` → `Ctrl-B 0`.
- Хуулахад `>` мөрүүд markdown quote болж эвдэрсэн байсныг terminal дээр харагдах хэлбэрт нь буцаав.

## Solution

```console
hacker@terminal-multiplexing~switching-windows-tmux:~$ cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{I6Qq4hx3sWbdqcxSkGsUl8HEQYK.0FM5IDOxwyMwEzM2EzW}
> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{I6Qq4hx3sWbdqcxSkGsUl8HEQYK.0FM5IDOxwyMwEzM2EzW}
hacker@terminal-multiplexing~switching-windows-tmux:~$
```

## Flag

```
pwn.college{I6Qq4hx3sWbdqcxSkGsUl8HEQYK.0FM5IDOxwyMwEzM2EzW}
```
