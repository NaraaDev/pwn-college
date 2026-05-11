hacker@commands~finding-files:/$ find / -name flag
find: ‘/root’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
/usr/lib/python3/dist-packages/pwnlib/flag
/usr/share/doc/python3-idna/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
/nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
/nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/h88mxp2mbgyj06vypwmqpy05idhwimnp-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/5qz6hgb1qzpvjrsw20wyiylx5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
/nix/store/c07wba3nrck81kdh0yg5h8rx22di35xi-radare2-6.0.4/share/radare2/6.0.4/flag
/nix/store/gfyhjlxav9nczmnanb3jxr73kb22yp42-rizin-0.8.1/share/rizin/flag
/nix/store/61dd247b72i7xnm0mw9qaxgfx3gs2lyy-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/sh1s72wwgvcq50kp830nlhm5cjpxmyh7-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/1wn496frzskd2drjwyyskk3g50rd1nbd-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
find: ‘/nix/var/nix/builds/nix-8-990530188’: Permission denied
find: ‘/nix/var/nix/builds/nix-8-3069189441’: Permission denied
hacker@commands~finding-files:/$ cat /usr/lib/python3/dist-packages/pwnlib/flag
cat: /usr/lib/python3/dist-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:/$ /usr/lib/python3/dist-packages/pwnlib/flag
bash: /usr/lib/python3/dist-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:/$ ./usr/lib/python3/dist-packages/pwnlib/flag
bash: ./usr/lib/python3/dist-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:/$ ./usr/lib/python3/dist-packages/pwnlib/flag/flag.py
bash: ./usr/lib/python3/dist-packages/pwnlib/flag/flag.py: Permission denied
hacker@commands~finding-files:/$ cat /usr/share/doc/python3-idna/flag
pwn.college{wq3lMnZZZBIaIY0Bl\_\_1lmTYppg.QXyMDO0wyMwEzM2EzW}hacker@commands~finding-files:/$
