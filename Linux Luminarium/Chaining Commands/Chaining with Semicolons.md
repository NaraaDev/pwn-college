# Chaining with Semicolons

> Module: **Linux Luminarium / Chaining Commands** · Challenge: `chaining-with-semicolons`

`/challenge/pwn` ба `/challenge/college`-ийг `;`-ээр нэг мөрөнд залгаж, ар араас нь ажиллуулж флаг авна.

## Тайлбар

- `;` нь Enter дарахтай адил — эхний команд дуусмагц дараагийнх нь ажиллана. Ялгаа нь зөвхөн prompt гарахгүй, хоёр командыг урьдчилж нэг мөрөнд бичдэг. `echo COLLEGE > pwn; cat pwn` нь хоёр тусдаа мөрөнд бичсэнтэй ижил үр дүнтэй.
- `;` нь эхний командын амжилт/бүтэлгүйтлийг **огт шалгадаггүй** — эхнийх алдаа өгсөн ч дараагийнх ажиллана (`&&`, `||`-оос ялгаатай, дараагийн level-үүдэд үзнэ).
- `/challenge/pwn` нь дараа нь `/challenge/college` дуудагдсан эсэхийг шалгадаг. Хоёр дахь командын замыг буруу бичихэд (`/challenge/r`, `/challenge/run` — тийм файл байхгүй) "did not chain it with /challenge/college" гэж сануулсан; зөв замаар нь залгахад флаг гарсан.

## Solution

```console
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn; /challenge/r
bash: /challenge/r: No such file or directory
It looks like you invoked /challenge/pwn, but did not chain it with
/challenge/college. Please try again! Remember, you can use ';' to separate two
commands and have them run one after the other.
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn; /challenge/run
bash: /challenge/run: No such file or directory
It looks like you invoked /challenge/pwn, but did not chain it with
/challenge/college. Please try again! Remember, you can use ';' to separate two
commands and have them run one after the other.
hacker@chaining~chaining-with-semicolons:~$ /challenge/r
bash: /challenge/r: No such file or directory
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{sFA6byVpYpmWqzJesGvH7VVOBFP.QX1UDO0wyMwEzM2EzW}
hacker@chaining~chaining-with-semicolons:~$
```

## Flag

```
pwn.college{sFA6byVpYpmWqzJesGvH7VVOBFP.QX1UDO0wyMwEzM2EzW}
```
