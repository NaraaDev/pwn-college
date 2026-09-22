# Your First Shell Script

> Module: **Linux Luminarium / Chaining Commands** · Challenge: `your-first-shell-script`

`/challenge/pwn` ба `/challenge/college` командуудыг `x.sh` файлд бичээд `bash x.sh`-аар ажиллуулж флаг авна.

## Тайлбар

- Олон командыг нэг мөрөнд залгах нь урт болоход тэдгээрийг файлд бичиж **shell script** болгоно. Мөр бүр нь тусдаа команд — `;`-ээр залгасантай адил дараалан ажиллана.
- `bash x.sh` — bash-ийг хэрэглэгчээс биш, `x.sh` файлаас команд уншихаар ажиллуулна. `.sh` өргөтгөл нь зөвхөн заншил, заавал биш.
- Текст засварлагч ашиглалгүй `echo '/challenge/pwn' > x.sh` (файл үүсгэх), `echo '/challenge/college' >> x.sh` (төгсгөлд нэмэх) гэж хоёр мөрт скриптийг shell-ээсээ шууд бичсэн. `>` дарж бичдэг, `>>` нэмдэг — хоёуланд нь `>` бичвэл эхний мөр алга болно.

## Solution

```console
hacker@chaining~your-first-shell-script:~$ echo '/challenge/pwn' > x.sh
hacker@chaining~your-first-shell-script:~$ echo '/challenge/college' >> x.sh
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{kTQya188RgRlrz6zx1dLochBVrS.QXxcDO0wyMwEzM2EzW}
hacker@chaining~your-first-shell-script:~$
```

## Flag

```
pwn.college{kTQya188RgRlrz6zx1dLochBVrS.QXxcDO0wyMwEzM2EzW}
```
