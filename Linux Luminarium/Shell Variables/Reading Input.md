# Reading Input

> Module: **Linux Luminarium / Shell Variables** · Challenge: `reading-input`

`read` builtin ашиглан стандарт оролтоос (stdin) утга уншиж хувьсагчид онооно.

## Тайлбар

- `read PWN` — stdin-ээс нэг мөр уншиж `PWN` хувьсагчид онооно. Командыг бичсэний дараа terminal хүлээж зогссон, `COLLEGE` гэж бичээд Enter дарсан.
- `read -p "Value: " PWN` гэж `-p` сонголтоор асуулт (prompt) харуулж бас болно.
- `read` нь shell builtin тул уншсан утга одоогийн shell-ийн хувьсагчид шууд хадгалагдана.

## Solution

```console
hacker@variables~reading-input:~$ read PWN
COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{0ccoXTgLUPWaX1E5mQV_tK6VcIb.QX4cTN0wyMwEzM2EzW}
```

## Flag

```
pwn.college{0ccoXTgLUPWaX1E5mQV_tK6VcIb.QX4cTN0wyMwEzM2EzW}
```
