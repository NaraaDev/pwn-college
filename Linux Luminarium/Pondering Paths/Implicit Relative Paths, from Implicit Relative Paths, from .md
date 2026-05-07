hacker@paths~implicit-relative-paths-from-:/$ /tmp/
bash: /tmp/: Is a directory
hacker@paths~implicit-relative-paths-from-:/$ ls
bin boot challenge dev etc flag home lib lib64 media mnt nix opt proc root run sbin srv sys tmp usr var
hacker@paths~implicit-relative-paths-from-:/$ ./tmp/
bash: ./tmp/: Is a directory
hacker@paths~implicit-relative-paths-from-:/$ cd tmp/
hacker@paths~implicit-relative-paths-from-:/tmp$ ls
hacker@paths~implicit-relative-paths-from-:/tmp$ cd /challenge/run
bash: cd: /challenge/run: Not a directory
hacker@paths~implicit-relative-paths-from-:/tmp$ /challenge/run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~implicit-relative-paths-from-:/tmp$ ls
hacker@paths~implicit-relative-paths-from-:/tmp$ cd ..
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{Ech_6OV2VXqP0UY1vAmvzGIBrYe.QX5QTN0wyMwEzM2EzW}
hacker@paths~implicit-relative-paths-from-:/$
