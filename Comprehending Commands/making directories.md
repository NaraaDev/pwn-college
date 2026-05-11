hacker@commands~making-directories:~$ ls
Desktop a leap rsa rsa.pub
hacker@commands~making-directories:~$ cd /tmp
hacker@commands~making-directories:/tmp$ ls
hacker@commands~making-directories:/tmp$ mkdir pwn
hacker@commands~making-directories:/tmp$ cd pwn/
hacker@commands~making-directories:/tmp/pwn$ mkdir college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Uh oh! /tmp/pwn/college does not exist. Please use the 'touch' command to
create it!
hacker@commands~making-directories:/tmp/pwn$ rm -rf cole
hacker@commands~making-directories:/tmp/pwn$ ls
college
hacker@commands~making-directories:/tmp/pwn$ rm -rf college/
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{McWA8Qxu8euSh_ttyxuMepVGxeG.QXxMDO0wyMwEzM2EzW}
