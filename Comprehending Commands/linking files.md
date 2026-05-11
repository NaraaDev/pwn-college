# Linking Files

> Module: **Comprehending Commands** · Challenge: `linking-files`

Symbolic link (зөөлөн холбоос) ашиглан `/challenge/catflag` программыг `/flag` файлыг уншуулах сорилт. Программ `/home/hacker/not-the-flag` гэсэн хатуу кодтой замаас унших тул тэр замд symlink үүсгэх шаардлагатай.

## Тайлбар

| Команд | Тайлбар |
|--------|---------|
| `/challenge/catflag` | `/home/hacker/not-the-flag` файлыг уншиж flag хэвлэдэг тусгай программ. |
| `ln -s <target> <link>` | Symbolic link үүсгэнэ. `target` — жинхэнэ файлын зам, `link` — шинэ холбоосын зам. |
| `rm -rf <path>` | Байгаа хугарсан symlink-г устгана. |
| `file <path>` | Файлын төрлийг шалгана (symlink эсэх, хаашаа зааж байгаа). |

Алдааны шийдэл:
- `ln -s flag /home/hacker/not-the-flag` → `flag` харьцангуй зам байсан тул `/home/hacker/flag` руу зааж, хугарсан symlink болов.
- `rm -rf /home/hacker/not-the-flag` → хугарсан symlink-г устгав.
- `ln -s /flag /home/hacker/not-the-flag` → **бүрэн зам** `/flag` ашиглан зөв symlink үүсгэв.

## Solution

```console
hacker@commands~linking-files:/challenge$ ./catflag
About to read out the /home/hacker/not-the-flag file!
cat: /home/hacker/not-the-flag: No such file or directory

hacker@commands~linking-files:/$ ln -s /flag /home/hacker/not-the-flag
ln: failed to create symbolic link '/home/hacker/not-the-flag': File exists

hacker@commands~linking-files:/$ rm -rf /home/hacker/not-the-flag
hacker@commands~linking-files:/$ ln -s /flag /home/hacker/not-the-flag

hacker@commands~linking-files:/$ file /home/hacker/not-the-flag
/home/hacker/not-the-flag: symbolic link to /flag

hacker@commands~linking-files:/$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{8zHoe34tbT-qOZyxd-G2j3ALtHg.QX5ETN1wyMwEzM2EzW}
```

## Гол сургамж

`ln -s` команд дахь target заавал **бүрэн (absolute) зам** байх ёстой. Харьцангуй зам ашиглавал symlink нь link-ийн байрлалаас нь хамааран хугарна.

## Flag

```
pwn.college{8zHoe34tbT-qOZyxd-G2j3ALtHg.QX5ETN1wyMwEzM2EzW}
```
