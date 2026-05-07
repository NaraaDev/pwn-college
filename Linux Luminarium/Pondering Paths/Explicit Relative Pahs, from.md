Desktop leap rsa rsa.pub
hacker@paths~explicit-relative-paths-from-:~$ cd Desktop/
hacker@paths~explicit-relative-paths-from-:~/Desktop$ cd ..
hacker@paths~explicit-relative-paths-from-:~$ cd ..
hacker@paths~explicit-relative-paths-from-:/home$ ls
hacker
hacker@paths~explicit-relative-paths-from-:/home$ cd ..
hacker@paths~explicit-relative-paths-from-:/$ cd challenge/
hacker@paths~explicit-relative-paths-from-:/challenge$ ls
Dockerfile run
hacker@paths~explicit-relative-paths-from-:/challenge$ ./run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~explicit-relative-paths-from-:/challenge$ cd ..
hacker@paths~explicit-relative-paths-from-:/$ challenge/run
Incorrect...
This challenge must be called with a relative path that explicitly starts with a `.`!
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{wDRcP_T0Toyk-XK98Vn3t8aX4yu.QXwUTN0wyMwEzM2EzW}
hacker@paths~explicit-relative-paths-from-:/$
