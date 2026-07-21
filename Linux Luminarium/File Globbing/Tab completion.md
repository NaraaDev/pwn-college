# Tab Completion

> Module: **Linux Luminarium / File Globbing** · Challenge: `tab-completion`

Файлын нэрэнд харагдахгүй тэмдэгт (zero-width space) шингээсэн тул нэрийг гараар бичиж давтахад boломжгүй; зөвхөн tab autocompletion ашиглан бодит нэрийг олж авна.

## Тайлбар

- `ls` хийхэд `pwncollege` шиг харагдах ч, `cd pwncollege` гэж бичихэд "Not a directory" гэсэн алдаа гарна — учир нь бодит нэрэнд `pwncollege` дараа U+200B (zero-width space) далд тэмдэгт орсон байдаг.
- Тэр тэмдэгтийг нүдээр харж, гараар давтан бичих боломжгүй тул Tab товч дарж autocomplete хийснээр shell бодит нэрийг (далд тэмдэгттэй хамт) бөглөнө.

## Solution

```console
hacker@globbing~tab-completion:/challenge$ cd pwncollege​ 
bash: cd: pwncollege​: Not a directory
hacker@globbing~tab-completion:/challenge$ ls
Dockerfile  pwncollege​
hacker@globbing~tab-completion:/challenge$ cat pwncollege​ 
pwn.college{wtPgmpgR88F91ItsYKno0CuLpt0.0FN0EzNxwyMwEzM2EzW}
```

## Flag

```
pwn.college{wtPgmpgR88F91ItsYKno0CuLpt0.0FN0EzNxwyMwEzM2EzW}
```
