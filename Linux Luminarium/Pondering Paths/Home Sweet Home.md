Writing the file to /home/hacker!
/challenge/run: line 29: /home/hacker: Is a directory
... and reading it back to you:
cat: /home/hacker: Is a directory
hacker@paths~home-sweet-home:~$ /challenge/run ~
Writing the file to /home/hacker!
/challenge/run: line 29: /home/hacker: Is a directory
... and reading it back to you:
cat: /home/hacker: Is a directory
hacker@paths~home-sweet-home:~$ /challenge/run
You must provide an argument to /challenge/run when you invoke it!
hacker@paths~home-sweet-home:~$ /challenge/run home/hacker
The argument you provided must not have been longer than 3 characters (it's
currently 11 characters long)!
hacker@paths~home-sweet-home:~$ /challenge/run /home/hacker
The argument you provided must not have been longer than 3 characters (it's
currently 12 characters long)!
hacker@paths~home-sweet-home:~$ /challenge/run run
The argument you provided is not an absolute path!
hacker@paths~home-sweet-home:~$ /challenge/run ~/a
Writing the file to /home/hacker/a!
... and reading it back to you:
pwn.college{I1naLyMiowKNcWjclWhqB6-5XVJ.QXzMDO0wyMwEzM2EzW}
hacker@paths~home-sweet-home:~$
