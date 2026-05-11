# Challenge Programs

> Module: **Start Here** · Challenge: `challenge-programs`

pwn.college дээр сорилт бүрд `/challenge` гэсэн директор автоматаар үүсэх ба дотор нь `solve` (заримдаа `run`) гэсэн program байдаг. Үүнийг ажиллуулж flag-аа авах.

## Тайлбар

- `/challenge` — root-аас эхлэх **absolute path**. Хаанаас ч хамаагүй, мөн өөрчлөгдөхгүй.
- `cd /challenge` — `cd` (change directory) тухайн директор руу шилжих комманд.
- `./solve` — одоогийн (`.`) директор доторх `solve` програмыг ажиллуулна. PATH-д ороогүй program-ыг ингэж дуудна.

## Solution

```console
hacker@start:~$ cd /challenge
hacker@start:/challenge$ ./solve
```

## Flag

```
pwn.college{4CDz9OSYVjx4Ha1Sm4WPCzC8hWH.QX0MDO0wyMwEzM2EzW}
```
