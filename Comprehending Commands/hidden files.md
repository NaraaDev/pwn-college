# Hidden Files

> Module: **Comprehending Commands** · Challenge: `hidden-files`

Linux дотор **`.`-аар эхэлсэн** файлууд **нуугдмал** (hidden) гэж тооцогддог. `ls` ердийн хэлбэрээр харуулдаггүй.

## Тайлбар

- `.` -аар эхэлдэг файл/директор: `.bash_history`, `.config`, `.ssh`, `.cache` гэх мэт **тохиргооны** файлууд ихэвчлэн нуугдмал.
- `ls -a` (all) — нуугдсан файлуудыг хамтад нь харуулна.
- `ls -la` — нарийвчилсан + нуугдсан хамт.
- Challenge: `/` доор `.flag-<random>` нэртэй нуугдсан файлд flag байгаа. `ls -a /`-аар нь олж, `cat`-аар уншина.

```bash
ls -a            # нуугдсан хамт
ls -la /         # / доорх бүх файл нарийвчилсан
cat /.flag-XXXX  # flag файлыг унш
```

## Solution

```console
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls
bin boot challenge dev etc home lib lib64 media mnt nix opt proc root run sbin srv sys tmp usr var
hacker@commands~hidden-files:/$ ls -a
. .. .dockerenv .flag-315772052330710 bin boot challenge dev etc home lib lib64 media mnt nix opt proc root run sbin srv sys tmp usr var
hacker@commands~hidden-files:/$ cat .flag-315772052330710
pwn.college{QB5xdSZaLMla0umGBA2NJDabnBz.QXwUDO0wyMwEzM2EzW}
```

## Flag

```
pwn.college{QB5xdSZaLMla0umGBA2NJDabnBz.QXwUDO0wyMwEzM2EzW}
```
