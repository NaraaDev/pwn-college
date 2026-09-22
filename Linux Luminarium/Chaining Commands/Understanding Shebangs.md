# Understanding Shebangs

> Module: **Linux Luminarium / Chaining Commands** · Challenge: `understanding-shebangs`

`#!/bin/bash` shebang-тай, `hack the planet` хэвлэдэг executable `/home/hacker/solve.sh` үүсгээд `/challenge/run`-аар шалгуулж флаг авна.

## Тайлбар

- Linux программыг ажиллуулахдаа өргөтгөлийг нь биш, файлын **эхний хэдэн байтыг** харж хэрхэн ажиллуулахаа шийднэ. Файл `#!` ("shebang")-аар эхэлбэл мөрийн үлдсэн хэсгийг интерпретаторын зам гэж үзээд `<интерпретатор> <файлын зам>` хэлбэрээр ажиллуулна: `./script.sh` → `/bin/bash ./script.sh`.
- Shebang заавал файлын **хамгийн эхний мөр** байх ёстой — өмнө нь хоосон мөр, зай байж болохгүй. `printf '#!/bin/bash\necho "hack the planet"\n'`-ээр яг тэр дарааллаар бичсэн.
- Shebang-гүй бол скрипт зөвхөн shell-ээс (`bash script.sh`) ажиллана; Python гэх мэт өөр программаас дуудахад ямар интерпретатор хэрэгтэйг мэдэхгүй. Түгээмэл shebang: `#!/bin/bash`, `#!/usr/bin/python3`, `#!/bin/sh` (bash-ийн энгийн, илүү нийцтэй өвөг).
- `chmod +x` өгсний дараа `/challenge/run` скриптийг ажиллуулж гаралтыг шалгаад флаг өгнө.
- Хуулсан session-д prompt мөрүүд байгаагүй тул доор нөхөж бичив.

## Solution

```console
hacker@chaining~understanding-shebangs:~$ printf '#!/bin/bash\necho "hack the planet"\n' > /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ chmod +x /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Perfect! Your flag:
Flag: pwn.college{0Z_PesnKPVHKuMRjsaBMby8bKRl.0VOzMDOxwyMwEzM2EzW}
```

## Flag

```
pwn.college{0Z_PesnKPVHKuMRjsaBMby8bKRl.0VOzMDOxwyMwEzM2EzW}
```
