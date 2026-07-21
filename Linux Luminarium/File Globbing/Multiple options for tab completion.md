# Multiple Options for Tab Completion

> Module: **Linux Luminarium / File Globbing** · Challenge: `multiple-options-for-tab-completion`

Ижил угтвартай олон файл байгаа тохиолдолд Tab дарахад автоматаар нэг рүү нь бөглөгдөхгүй, зөвхөн бүх файлд нийтлэг хэсэг хүртэл л дуусгана.

## Тайлбар

- `/challenge/files/` дотор `pwncollege` угтвартай хэд хэдэн файл байгаа тул Tab дарахад ялгаатай хэсгээс өмнөх нийтлэг угтвар хүртэл л autocomplete хийгдэнэ.
- Үлдсэн ялгаатай хэсгийг гараар нэмж бичих буюу дахин Tab дарж (давхар Tab) боломжит сонголтуудыг харах шаардлагатай.
- Зорилтот файл нь `pwncollege-flag` нэртэй байсан бөгөөд агуулгыг нь `cat`-аар уншсанаар флаг гарч ирнэ.

## Solution

```console
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat /challenge/files/pwncollege-flag
pwn.college{Q21-rOxzsBDiBmJlXFky7YxYAof.0lN0EzNxwyMwEzM2EzW}
```

## Flag

```
pwn.college{Q21-rOxzsBDiBmJlXFky7YxYAof.0lN0EzNxwyMwEzM2EzW}
```
