/challenge/run
Starting level 1.
Incorrect...
You are not currently in the /var/lib/apt/lists directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /var/lib/apt/lists
hacker@paths~position-elsewhere:/var/lib/apt/lists$ /challenge/run
Starting level 1.
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Moving on to level 2
Please use the `cd` utility to change directory to /etc
hacker@paths~position-elsewhere:/var/lib/apt/lists$ cd /etc
hacker@paths~position-elsewhere:/etc$ ls
alternatives debian_version group- ld.so.conf networks python3.12 security sudo_logsrvd.conf
apparmor.d default gshadow ld.so.conf.d nsswitch.conf rc0.d selinux sudoers
apt dpkg gshadow- legal opt rc1.d services sudoers.d
bash.bashrc e2scrub.conf host.conf libaudit.conf os-release rc2.d shadow sysctl.conf
bashrc environment hostname localtime pam.conf rc3.d shadow- sysctl.d
bindresvport.blacklist ethertypes hosts login.defs pam.d rc4.d shells systemd
ca-certificates fstab init.d logrotate.d passwd rc5.d skel terminfo
ca-certificates.conf gai.conf inputrc lsb-release passwd- rc6.d ssl timezone
cloud gdb issue machine-id perl rcS.d subgid tmpfiles.d
cron.d gnutls issue.net manpath.config profile resolv.conf subgid- update-motd.d
cron.daily gprofng.rc john mime.types profile.d rmt subuid xattr.conf
cron.weekly groff kernel mke2fs.conf protocols rpc subuid-
debconf.conf group ld.so.cache mtab python3 screenrc sudo.conf
hacker@paths~position-elsewhere:/etc$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Moving on to level 3
Please use the `cd` utility to change directory to /home
hacker@paths~position-elsewhere:/etc$ cd /home/
hacker@paths~position-elsewhere:/home$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Moving on to level 4
Please use the `cd` utility to change directory to /usr/include
hacker@paths~position-elsewhere:/home$ cd /usr/include
hacker@paths~position-elsewhere:/usr/include$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Moving on to level 5
Please use the `cd` utility to change directory to /usr/share/build-essential
hacker@paths~position-elsewhere:/usr/include$ cd /usr/share/build-essential
hacker@paths~position-elsewhere:/usr/share/build-essential$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{Ys42077PC_xE0HyAJXVFFSSw2lB.QX3QTN0wyMwEzM2EzW}
hacker@paths~position-elsewhere:/usr/share/build-essential$
