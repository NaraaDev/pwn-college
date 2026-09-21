# Permission Tweaking Practice

> Module: **Linux Luminarium / Perceiving Permission** · Challenge: `permission-tweaking-practice`

`/challenge/pwn`-ийн эрхийг `chmod WHO+/-WHAT`-аар 8 удаа дараалан заасан хэлбэрт оруулж, дараа нь `/flag`-ийг `chmod +r`-ээр уншигдахаар болгоно.

## Тайлбар

- `/challenge/run` нь `/challenge/pwn`-ийн эрхийг 8 удаа дараалан заасан хэлбэрт оруулахыг шаардана; буруу тавибал тоглоом эхнээс эхэлнэ. 8 удаа зөв бол `/flag`-ийн эзнийг `hacker` болгож, `chmod`-оор уншигдахаар болгох боломж өгнө.
- `run` хэвлэсэн **Current** ба **Needed** мөрүүдийг харьцуулж, зөвхөн ялгаатай битүүдийг `WHO+/-WHAT`-аар засна. `-` мөр = байгаа эрх, `*` мөр = байхгүй эрх.
- Ашигласан mode-ууд: `o-x`, `a-wx`, `go+w`, `o-rw`, `a-rwx`, `o+x`, `uo+r` — `WHO` хэсэгт `go`, `uo` гэх мэт хэд хэдэн зэрэг өгч болно.
- Capture Round 2-оос эхэлсэн — Round 1 нь энэ transcript-аас өмнө шийдэгдсэн.
- `/challenge/run` арын дэвсгэрт эрхийг ажиглаж байдаг тул `chmod`-ын дараа шууд дараагийн round хэвлэгдэнэ. Гурван удаа `chmod`-ын араас `/challenge/run`-ийг дахин бичсэн тул Round 3, Round 8 болон эцсийн блок давхар хэвлэгдсэн — доор `...` мөрөөр товчилсон.
- Бүх round-ыг давсны дараа `/flag` нь `---------` (эзэн нь `hacker`) → `cat` хийхэд `Permission denied`; `chmod +r /flag` → уншигдана.

## Solution

```console
hacker@permissions~permission-tweaking-practice:~$ ls -l /flag
-r-------- 1 root root 60 Sep 21 14:45 /flag
hacker@permissions~permission-tweaking-practice:~$ ls -l /challenge/pwn
-rwxr--rwx 1 hacker hacker 0 Sep 21 14:45 /challenge/pwn
hacker@permissions~permission-tweaking-practice:~$ /challenge/run
Round 2 of 8!

Current permissions of "/challenge/pwn": rwxr--rwx
- the user does have read permissions
- the user does have write permissions
- the user does have execute permissions
- the group does have read permissions
* the group doesn't have write permissions
* the group doesn't have execute permissions
- the world does have read permissions
- the world does have write permissions
- the world does have execute permissions

Needed permissions of "/challenge/pwn": rwxr--rw-
- the user does have read permissions
- the user does have write permissions
- the user does have execute permissions
- the group does have read permissions
* the group doesn't have write permissions
* the group doesn't have execute permissions
- the world does have read permissions
- the world does have write permissions
* the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod o-x /challenge/pwn
/challenge/run
You set the correct permissions!
Round 3 of 8!

Current permissions of "/challenge/pwn": rwxr--rw-
- the user does have read permissions
- the user does have write permissions
- the user does have execute permissions
- the group does have read permissions
* the group doesn't have write permissions
* the group doesn't have execute permissions
- the world does have read permissions
- the world does have write permissions
* the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r--r--r--
- the user does have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
- the group does have read permissions
* the group doesn't have write permissions
* the group doesn't have execute permissions
- the world does have read permissions
* the world doesn't have write permissions
* the world doesn't have execute permissions
... (давхар бичсэн /challenge/run ижил «Round 3 of 8» блокийг дахин хэвлэв) ...
hacker@permissions~permission-tweaking-practice:~$ chmod a-wx /challenge/pwn
You set the correct permissions!
Round 4 of 8!

Current permissions of "/challenge/pwn": r--r--r--
- the user does have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
- the group does have read permissions
* the group doesn't have write permissions
* the group doesn't have execute permissions
- the world does have read permissions
* the world doesn't have write permissions
* the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r--rw-rw-
- the user does have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
- the group does have read permissions
- the group does have write permissions
* the group doesn't have execute permissions
- the world does have read permissions
- the world does have write permissions
* the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod go+w /challenge/pwn
You set the correct permissions!
Round 5 of 8!

Current permissions of "/challenge/pwn": r--rw-rw-
- the user does have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
- the group does have read permissions
- the group does have write permissions
* the group doesn't have execute permissions
- the world does have read permissions
- the world does have write permissions
* the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r--rw----
- the user does have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
- the group does have read permissions
- the group does have write permissions
* the group doesn't have execute permissions
* the world doesn't have read permissions
* the world doesn't have write permissions
* the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod o-rw /challenge/pwn
You set the correct permissions!
Round 6 of 8!

Current permissions of "/challenge/pwn": r--rw----
- the user does have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
- the group does have read permissions
- the group does have write permissions
* the group doesn't have execute permissions
* the world doesn't have read permissions
* the world doesn't have write permissions
* the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": ---------
* the user doesn't have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
* the group doesn't have read permissions
* the group doesn't have write permissions
* the group doesn't have execute permissions
* the world doesn't have read permissions
* the world doesn't have write permissions
* the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod a-rwx /challenge/pwn
You set the correct permissions!
Round 7 of 8!

Current permissions of "/challenge/pwn": ---------
* the user doesn't have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
* the group doesn't have read permissions
* the group doesn't have write permissions
* the group doesn't have execute permissions
* the world doesn't have read permissions
* the world doesn't have write permissions
* the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": --------x
* the user doesn't have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
* the group doesn't have read permissions
* the group doesn't have write permissions
* the group doesn't have execute permissions
* the world doesn't have read permissions
* the world doesn't have write permissions
- the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod o+x /challenge/pwn
/challenge/run
You set the correct permissions!
Round 8 of 8!

Current permissions of "/challenge/pwn": --------x
* the user doesn't have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
* the group doesn't have read permissions
* the group doesn't have write permissions
* the group doesn't have execute permissions
* the world doesn't have read permissions
* the world doesn't have write permissions
- the world does have execute permissions

Needed permissions of "/challenge/pwn": r-----r-x
- the user does have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
* the group doesn't have read permissions
* the group doesn't have write permissions
* the group doesn't have execute permissions
- the world does have read permissions
* the world doesn't have write permissions
- the world does have execute permissions
... (давхар бичсэн /challenge/run ижил «Round 8 of 8» блокийг дахин хэвлэв) ...
hacker@permissions~permission-tweaking-practice:~$ chmod uo+r /challenge/pwn
/challenge/run
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
* the user doesn't have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
* the group doesn't have read permissions
* the group doesn't have write permissions
* the group doesn't have execute permissions
* the world doesn't have read permissions
* the world doesn't have write permissions
* the world doesn't have execute permissions
... (давхар бичсэн /challenge/run ижил «You've solved all 8 rounds» блокийг дахин хэвлэв) ...
hacker@permissions~permission-tweaking-practice:~$ cat /flag
cat: /flag: Permission denied
hacker@permissions~permission-tweaking-practice:~$ chmod +r /flag
hacker@permissions~permission-tweaking-practice:~$ cat /flag
pwn.college{Qks3Q9kfPEHB-WaR7a5BuBmnf8N.QXwEjN0wyMwEzM2EzW}
hacker@permissions~permission-tweaking-practice:~$
```

## Flag

```
pwn.college{Qks3Q9kfPEHB-WaR7a5BuBmnf8N.QXwEjN0wyMwEzM2EzW}
```
