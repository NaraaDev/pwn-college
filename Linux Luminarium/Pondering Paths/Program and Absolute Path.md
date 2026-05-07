bin boot challenge dev etc flag home lib lib64 media mnt nix opt proc root run sbin srv sys tmp usr var
hacker@paths~program-and-absolute-paths:/$ cd challenge/
hacker@paths~program-and-absolute-paths:/challenge$ ls
Dockerfile run
hacker@paths~program-and-absolute-paths:/challenge$ ./run
Incorrect...
You did not call this challenge using an absolute path!
An absolute path is anchored at the root of the filesystem, so it starts with /
hacker@paths~program-and-absolute-paths:/challenge$ run
bash: run: command not found
hacker@paths~program-and-absolute-paths:/challenge$ cd ..
hacker@paths~program-and-absolute-paths:/$ challenge/run
Incorrect...
You did not call this challenge using an absolute path!
An absolute path is anchored at the root of the filesystem, so it starts with /
hacker@paths~program-and-absolute-paths:/$ ./challenge/run
Incorrect...
You did not call this challenge using an absolute path!
An absolute path is anchored at the root of the filesystem, so it starts with /
hacker@paths~program-and-absolute-paths:/$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{Qzej67SLFi7ULtC59tUcW2cPpDe.QX1QTN0wyMwEzM2EzW}
hacker@paths~program-and-absolute-paths:/$
