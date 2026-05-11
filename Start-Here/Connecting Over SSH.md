# Connecting Over SSH

> Module: **Start Here** · Challenge: `connecting-over-ssh`

`ssh` ашиглан pwn.college сервер рүү алсаас холбогдох. Browser терминал биш, өөрийн локал терминалаар орох.

## Тайлбар

- **SSH (Secure Shell)** — алсын машин руу шифрлэгдсэн сувгаар нэвтэрч комманд ажиллуулах протокол.
- **SSH key** — нууц үг оронд хосолсон түлхүүр (private/public). pwn.college дээрх *Settings → SSH Key* хэсэгт нийтийн (`~/.ssh/id_rsa.pub`) түлхүүрээ оруулна.

```bash
# Локал машин дээр SSH key үүсгэх
ssh-keygen -t ed25519

# Холбогдох
ssh hacker@pwn.college
```

## Flag

```
pwn.college{0bzxwGqwmLHoaQD3oFGhvP7f9KV.0VNyQTMywyMwEzM2EzW}
```
