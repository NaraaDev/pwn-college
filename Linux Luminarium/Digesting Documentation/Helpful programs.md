hacker@man~helpful-programs:/challenge$ ls
Dockerfile challenge
hacker@man~helpful-programs:/challenge$ cha
bash: cha: command not found
hacker@man~helpful-programs:/challenge$ ./challenge
No options specified.
hacker@man~helpful-programs:/challenge$ ./challenge -h
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

options:
-h, --help show this help message and exit
--fortune read your fortune
-v, --version get the version number
-g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
get the flag, if given the correct value
-p, --print-value print the value that will cause the -g option to give you the flag
hacker@man~helpful-programs:/challenge$ ./challenge --help
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

options:
-h, --help show this help message and exit
--fortune read your fortune
-v, --version get the version number
-g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
get the flag, if given the correct value
-p, --print-value print the value that will cause the -g option to give you the flag
hacker@man~helpful-programs:/challenge$ ./challenge -g
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]
a challenge to make you ask for help: error: argument -g/--give-the-flag: expected one argument
hacker@man~helpful-programs:/challenge$ ./challenge -p
The secret value is: 866
hacker@man~helpful-programs:/challenge$ ./challenge -g 866
Correct usage! Your flag: pwn.college{866mVPTQxJeC5UA5MXOEEiAYFvu.QX3IDO0wyMwEzM2EzW}
