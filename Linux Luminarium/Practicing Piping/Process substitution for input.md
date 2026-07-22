# Process Substitution For Input

> Module: **Linux Luminarium / Practicing Piping** · Challenge: `process-substitution-for-input`

`<(...)` процесс орлуулалт (process substitution) ашиглан хоёр программын гаралтыг файл мэт `diff`-д шууд өгнө.

## Тайлбар

- `diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)` — хоёр командын гаралтыг тус тусад нь `<(...)` дотор ажиллуулж, `diff` тэдгээрийг ердийн файл мэт харьцуулна.
- Завсрын файл үүсгэх шаардлагагүйгээр хоёр гаралтын ялгааг шууд харах боломжтой болно.
- Ялгаа нь `print_decoys_and_flag` дээр нэмэлт мөр болж гарч ирсэн бөгөөд тэр нь флаг байв.

## Solution

```console
hacker@piping~process-substitution-for-input:~$ diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)
77a78
> pwn.college{MM7jKFHHZVOwpYGky-rCcTjGtTg.0lNwMDOxwyMwEzM2EzW}
```

## Flag

```
pwn.college{MM7jKFHHZVOwpYGky-rCcTjGtTg.0lNwMDOxwyMwEzM2EzW}
```
