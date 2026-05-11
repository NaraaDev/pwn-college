hacker@commands~linking-files:~$ ls
Desktop a leap rsa rsa.pub
hacker@commands~linking-files:~$ cd /challenge/
hacker@commands~linking-files:/challenge$ ls
Dockerfile catflag
hacker@commands~linking-files:/challenge$ ./catflag
About to read out the /home/hacker/not-the-flag file!
cat: /home/hacker/not-the-flag: No such file or directory
hacker@commands~linking-files:/challenge$ cd /flag
bash: cd: /flag: Not a directory
hacker@commands~linking-files:/challenge$ ls
Dockerfile catflag
hacker@commands~linking-files:/challenge$ cd ..
hacker@commands~linking-files:/$ ls
bin boot challenge dev etc flag home lib lib64 media mnt nix opt proc root run sbin srv sys tmp usr var
hacker@commands~linking-files:/$ ./f
bash: ./f: No such file or directory
hacker@commands~linking-files:/$ cat flag
cat: flag: Permission denied
hacker@commands~linking-files:/$ ln -s
ln: missing file operand
Try 'ln --help' for more information.
hacker@commands~linking-files:/$ ln -s flag
ln: failed to create symbolic link './flag': File exists
hacker@commands~linking-files:/$ ln -s flag /home/hacker/not-the-flag
hacker@commands~linking-files:/$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
cat: /home/hacker/not-the-flag: No such file or directory
hacker@commands~linking-files:/$ cd /home/hacker/
hacker@commands~linking-files:~$ ls
Desktop a leap not-the-flag rsa rsa.pub
hacker@commands~linking-files:~$ cat not-the-flag
cat: not-the-flag: No such file or directory
hacker@commands~linking-files:~$ cd not-the-flag
bash: cd: not-the-flag: No such file or directory
hacker@commands~linking-files:~$ file not-the-flag
not-the-flag: broken symbolic link to flag
hacker@commands~linking-files:~$ symbolic
bash: symbolic: command not found
hacker@commands~linking-files:~$ file ~/flag
/home/hacker/flag: cannot open `/home/hacker/flag' (No such file or directory)
hacker@commands~linking-files:~$ ls
Desktop  a  leap  not-the-flag  rsa  rsa.pub
hacker@commands~linking-files:~$ cd ..
hacker@commands~linking-files:/home$ ls
hacker
hacker@commands~linking-files:/home$ cd ..
hacker@commands~linking-files:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib64  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~linking-files:/$ file flag 
flag: regular file, no read permission
hacker@commands~linking-files:/$ ls -s flag /home/hacker/not-the-flag
4 /home/hacker/not-the-flag  4 flag
hacker@commands~linking-files:/$ cat ~/not-the-flag 
cat: /home/hacker/not-the-flag: No such file or directory
hacker@commands~linking-files:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib64  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~linking-files:/$ file ~/not-the-flag 
/home/hacker/not-the-flag: broken symbolic link to flag
hacker@commands~linking-files:/$ symbolic link to /flag 
bash: symbolic: command not found
hacker@commands~linking-files:/$ cat /flag 
cat: /flag: Permission denied
hacker@commands~linking-files:/$ cat ~/not-the-flag 
cat: /home/hacker/not-the-flag: No such file or directory
hacker@commands~linking-files:/$ ln -s /flag /home/hacker/not-the-flag 
ln: failed to create symbolic link '/home/hacker/not-the-flag': File exists
hacker@commands~linking-files:/$ rm -rf /home/hacker/not-the-flag
hacker@commands~linking-files:/$ ln -s /flag /home/hacker/not-the-flag 
hacker@commands~linking-files:/$ cat ~/not-the-flag 
cat: /home/hacker/not-the-flag: Permission denied
hacker@commands~linking-files:/$ file /flag 
/flag: regular file, no read permission
hacker@commands~linking-files:/$ file /homer/hacker/not-the-flag
/homer/hacker/not-the-flag: cannot open `/homer/hacker/not-the-flag' (No such file or directory)
hacker@commands~linking-files:/$ file /home/hacker/not-the-flag
/home/hacker/not-the-flag: symbolic link to /flag
hacker@commands~linking-files:/$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{8zHoe34tbT-qOZyxd-G2j3ALtHg.QX5ETN1wyMwEzM2EzW}
