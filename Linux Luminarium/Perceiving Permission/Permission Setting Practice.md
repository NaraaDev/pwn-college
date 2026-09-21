# Permissions Setting Practice

> Module: **Linux Luminarium / Perceiving Permission** · Challenge: `permissions-setting-practice`

`chmod`-ийн `=` болон `,`-залгаа шаардсан 8 round-ыг давж, `/flag`-ийг `chmod +r`-ээр уншина.

## Тайлбар

- `chmod`-д `=` ашиглавал тухайн `WHO`-ийн эрхийг **бүхэлд нь дарж** тавина: `u=rw` (execute арилна), `o=x` (read/write арилна), `a=rwx`. Хэд хэдэн mode-ийг `,`-оор залгана: `u=rw,g=r`, `a=r,u=rw`.
- `o=-` нь бүх эрхийг тэглэнэ: `=`-ийн ард орсон `-` нь "юу ч биш" утгатай, харин `o-r`-ийн `-` нь тодорхой битийг хасах утгатай — өөр контекст.
- Энэ level-ийн зорилго `=` ба `,`-залгаа боловч бүх round-ыг `,`-оор залгасан `+`/`-` mode-оор (`u-r,g+x`, `u+r,u-w,g-x,o-r,o+x`, ...) шийдсэн — ажилласан ч `=`-ээр илүү богино: Round 2 `u=r,g=r,o=x`, Round 4 `u=-,g=rx,o=-`, Round 6 `ug=-,o=rwx`, Round 8 `u=rw,g=rx,o=wx`.
- `run`-ийн **Current** / **Needed** блокуудыг бүрэн оруулав; `-` мөр = байгаа эрх, `*` мөр = байхгүй эрх.
- 8 round-ын дараа `/flag` нь `---------` (эзэн `hacker`) → `chmod +r /flag` → `cat /flag`.

## Solution

```console
hacker@permissions~permissions-setting-practice:~$ /challenge/run
Round 1 of 8!

Current permissions of "/challenge/pwn": rw-r--r--
- the user does have read permissions
- the user does have write permissions
* the user doesn't have execute permissions
- the group does have read permissions
* the group doesn't have write permissions
* the group doesn't have execute permissions
- the world does have read permissions
* the world doesn't have write permissions
* the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -w-r-xr--
* the user doesn't have read permissions
- the user does have write permissions
* the user doesn't have execute permissions
- the group does have read permissions
* the group doesn't have write permissions
- the group does have execute permissions
- the world does have read permissions
* the world doesn't have write permissions
* the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u-r,g+x /challenge/pwn
You set the correct permissions!
Round 2 of 8!

Current permissions of "/challenge/pwn": -w-r-xr--
* the user doesn't have read permissions
- the user does have write permissions
* the user doesn't have execute permissions
- the group does have read permissions
* the group doesn't have write permissions
- the group does have execute permissions
- the world does have read permissions
* the world doesn't have write permissions
* the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r--r----x
- the user does have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
- the group does have read permissions
* the group doesn't have write permissions
* the group doesn't have execute permissions
* the world doesn't have read permissions
* the world doesn't have write permissions
- the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u+r,u-w,g-x,o-r,o+x /challenge/pwn
You set the correct permissions!
Round 3 of 8!

Current permissions of "/challenge/pwn": r--r----x
- the user does have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
- the group does have read permissions
* the group doesn't have write permissions
* the group doesn't have execute permissions
* the world doesn't have read permissions
* the world doesn't have write permissions
- the world does have execute permissions

Needed permissions of "/challenge/pwn": r---wx--x
- the user does have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
* the group doesn't have read permissions
- the group does have write permissions
- the group does have execute permissions
* the world doesn't have read permissions
* the world doesn't have write permissions
- the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod g-r,g+wx /challenge/pwn
You set the correct permissions!
Round 4 of 8!

Current permissions of "/challenge/pwn": r---wx--x
- the user does have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
* the group doesn't have read permissions
- the group does have write permissions
- the group does have execute permissions
* the world doesn't have read permissions
* the world doesn't have write permissions
- the world does have execute permissions

Needed permissions of "/challenge/pwn": ---r-x---
* the user doesn't have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
- the group does have read permissions
* the group doesn't have write permissions
- the group does have execute permissions
* the world doesn't have read permissions
* the world doesn't have write permissions
* the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u-r,g+r,g-w,o-x /challenge/pwn
You set the correct permissions!
Round 5 of 8!

Current permissions of "/challenge/pwn": ---r-x---
* the user doesn't have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
- the group does have read permissions
* the group doesn't have write permissions
- the group does have execute permissions
* the world doesn't have read permissions
* the world doesn't have write permissions
* the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rwx-w-r-x
- the user does have read permissions
- the user does have write permissions
- the user does have execute permissions
* the group doesn't have read permissions
- the group does have write permissions
* the group doesn't have execute permissions
- the world does have read permissions
* the world doesn't have write permissions
- the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u+rwx,g-rx,g+w,o+rx /challenge/pwn
You set the correct permissions!
Round 6 of 8!

Current permissions of "/challenge/pwn": rwx-w-r-x
- the user does have read permissions
- the user does have write permissions
- the user does have execute permissions
* the group doesn't have read permissions
- the group does have write permissions
* the group doesn't have execute permissions
- the world does have read permissions
* the world doesn't have write permissions
- the world does have execute permissions

Needed permissions of "/challenge/pwn": ------rwx
* the user doesn't have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
* the group doesn't have read permissions
* the group doesn't have write permissions
* the group doesn't have execute permissions
- the world does have read permissions
- the world does have write permissions
- the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod ug-rwx,o+w /challenge/pwn
You set the correct permissions!
Round 7 of 8!

Current permissions of "/challenge/pwn": ------rwx
* the user doesn't have read permissions
* the user doesn't have write permissions
* the user doesn't have execute permissions
* the group doesn't have read permissions
* the group doesn't have write permissions
* the group doesn't have execute permissions
- the world does have read permissions
- the world does have write permissions
- the world does have execute permissions

Needed permissions of "/challenge/pwn": -wx---rw-
* the user doesn't have read permissions
- the user does have write permissions
- the user does have execute permissions
* the group doesn't have read permissions
* the group doesn't have write permissions
* the group doesn't have execute permissions
- the world does have read permissions
- the world does have write permissions
* the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u+wx,o-x /challenge/pwn
You set the correct permissions!
Round 8 of 8!

Current permissions of "/challenge/pwn": -wx---rw-
* the user doesn't have read permissions
- the user does have write permissions
- the user does have execute permissions
* the group doesn't have read permissions
* the group doesn't have write permissions
* the group doesn't have execute permissions
- the world does have read permissions
- the world does have write permissions
* the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw-r-x-wx
- the user does have read permissions
- the user does have write permissions
* the user doesn't have execute permissions
- the group does have read permissions
* the group doesn't have write permissions
- the group does have execute permissions
* the world doesn't have read permissions
- the world does have write permissions
- the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u+r,u-x,g+rx,o-r,o+x /challenge/pwn
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
hacker@permissions~permissions-setting-practice:~$ chmod +r /flag
hacker@permissions~permissions-setting-practice:~$ cat /flag
pwn.college{s6mzesqGdhtf_pd5QzuVwgiNIvE.QXzETO0wyMwEzM2EzW}
hacker@permissions~permissions-setting-practice:~$
```

## Flag

```
pwn.college{s6mzesqGdhtf_pd5QzuVwgiNIvE.QXzETO0wyMwEzM2EzW}
```
