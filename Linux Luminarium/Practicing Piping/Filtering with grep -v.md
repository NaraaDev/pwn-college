# Filtering With grep -v

> Module: **Linux Luminarium / Practicing Piping** · Challenge: `filtering-with-grep-v`

`grep -v` ашиглан тодорхой pattern агуулсан мөрүүдийг **хасаж**, үлдсэн (флаг агуулсан) мөрийг л харна.

## Тайлбар

- `/challenge/run | grep -v DECOY` — challenge программын гаралтаас `DECOY` гэсэн үг агуулсан бүх decoy мөрүүдийг шүүж хаяна.
- `-v` (invert match) флаг нь pattern-тай **таарахгүй** мөрүүдийг л хэвлэдэг, ингэснээр олон decoy мөрний дунд байгаа жинхэнэ флаг илэрхий гарч ирнэ.

## Solution

```console
hacker@piping~filtering-with-grep-v:~$ /challenge/run | grep -v DECOY
pwn.college{M-bxtjWm2OZyPDQpEmlDRGKVVTZ.0FOxEzNxwyMwEzM2EzW}
```

## Flag

```
pwn.college{M-bxtjWm2OZyPDQpEmlDRGKVVTZ.0FOxEzNxwyMwEzM2EzW}
```
