hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls
TRACE bin boot challenge dev etc flag home lib lib64 media mnt nix opt proc root run sbin srv sys tmp usr var
hacker@commands~an-epic-filesystem-quest:/$ cat TRACE
Congratulations, you found the clue!
The next clue is in: /usr/lib/x86_64-linux-gnu/perl/5.38.2/auto/NDBM_File

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/$ cd /usr/lib/x86_64-linux-gnu/perl/5.38.2/auto/NDBM_File
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl/5.38.2/auto/NDBM_File$ ls
NDBM_File.so TEASER
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl/5.38.2/auto/NDBM_File$ cat TEASER
Lucky listing!
The next clue is in: /usr/lib/python3/dist-packages/pip/\_internal/metadata/**pycache**

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl/5.38.2/auto/NDBM_File$ cd /usr/lib/python3/dist-packages/pip/\_internal/metadata/**pycache**
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/pip/\_internal/metadata/**pycache**$ ls -a
. .. .SECRET **init**.cpython-312.pyc \_json.cpython-312.pyc base.cpython-312.pyc pkg_resources.cpython-312.pyc
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/pip/\_internal/metadata/**pycache**$ cat .SECRET
Congratulations, you found the clue!
The next clue is in: /usr/lib/python3/dist-packages/pwnlib/data/elf/relro/**pycache**

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/pip/\_internal/metadata/**pycache**$ cat /usr/lib/python3/dist-packages/pwnlib/data/elf/relro/**pycache**/
NUGGET-TRAPPED **init**.cpython-312.pyc  
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/pip/\_internal/metadata/**pycache**$ ls /usr/lib/python3/dist-packages/pwnlib/data/elf/relro/**pycache**
NUGGET-TRAPPED **init**.cpython-312.pyc
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/pip/\_internal/metadata/**pycache**$ cat /usr/lib/python3/dist-packages/pwnlib/data/elf/relro/**pycache**/NUGGET-TRAPPED
Tubular find!
The next clue is in: /usr/include/linux/nfsd
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/pip/\_internal/metadata/**pycache**$ cd /usr/include/linux/nfsd
hacker@commands~an-epic-filesystem-quest:/usr/include/linux/nfsd$ ls
HINT cld.h debug.h export.h stats.h
hacker@commands~an-epic-filesystem-quest:/usr/include/linux/nfsd$ ls -a
. .. HINT cld.h debug.h export.h stats.h
hacker@commands~an-epic-filesystem-quest:/usr/include/linux/nfsd$ cat HINT
Congratulations, you found the clue!
The next clue is in: /usr/share/doc/sudo
hacker@commands~an-epic-filesystem-quest:/usr/include/linux/nfsd$ cd /usr/share/doc/sudo
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/sudo$ ls
CONTRIBUTING.md HISTORY.md NEWS.gz OPTIONS README.md TROUBLESHOOTING.md.gz changelog.Debian.gz examples
CONTRIBUTORS.md.gz NEWS.Debian.gz NOTE README.Debian SECURITY.md UPGRADE.md.gz copyright
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/sudo$ ls -a
. CONTRIBUTING.md HISTORY.md NEWS.gz OPTIONS README.md TROUBLESHOOTING.md.gz changelog.Debian.gz examples
.. CONTRIBUTORS.md.gz NEWS.Debian.gz NOTE README.Debian SECURITY.md UPGRADE.md.gz copyright
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/sudo$ cat SECURITY.md
Sudo Security Policy
====================

The Sudo Project takes security seriously. If you believe you have found a security vulnerability in Sudo, you can report it to us as described below.

## Reporting Security Issues

**Do not report security vulnerabilities through public GitHub issues or Bugzilla.**

Instead, report them via email to <Todd.Miller@sudo.ws>. You may encrypt your message with PGP if you would like. The current PGP key has the fingerprint 59D1 E9CC BA2B 3767 04FD D35B A9F4 C021 CEA4 70FB and may be downloaded from [the sudo.ws web site](https://www.sudo.ws/dist/PGPKEYS) or the [OpenPGP Key Server](https://keys.openpgp.org/search?q=0xa9f4c021cea470fb).

We try to respond to security issues in a timely manner but understand that Sudo is a volunteer project.

Include as much of the following information as possible to help us better understand the nature and scope of the potential issue:

- Type of issue (e.g. buffer overflow, privilege escalation, etc.)
- Full paths of source file(s) related to the issue
- The location of the affected source code (tag/branch/commit or direct URL)
- Any special configuration required to reproduce the issue
- The operating system and/or distro affected
- Step-by-step instructions to reproduce the issue
- Proof-of-concept or exploit code (if possible)
- Impact of the issue, including how an attacker might exploit the issue

This information will help us triage your report more quickly.

As a volunteer-led project, we are not able to offer bug bounties.
However, we'd be happy to send you Sudo stickers as a way of saying
thank you!

## Preferred Languages

We prefer all communications to be in English.

## Disclosure Policy

The Sudo Project follows the principle of [Coordinated Vulnerability Disclosure](https://vuls.cert.org/confluence/display/CVD/Executive+Summary). Disclosure is usually coordinated using the [distros mailing list](https://oss-security.openwall.org/wiki/mailing-lists/distros).

## Security Advisories

The Sudo web site contains an archive of [sudo security advisories](https://www.sudo.ws/security/advisories/).
Additionally, information about vulnerabilities in sudo is sent to the
[oss-security mailing list](https://oss-security.openwall.org/wiki/mailing-lists/oss-security) once the information becomes public.
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/sudo$ ls -a
. CONTRIBUTING.md HISTORY.md NEWS.gz OPTIONS README.md TROUBLESHOOTING.md.gz changelog.Debian.gz examples
.. CONTRIBUTORS.md.gz NEWS.Debian.gz NOTE README.Debian SECURITY.md UPGRADE.md.gz copyright
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/sudo$ cat NOTE
Great sleuthing!
The next clue is in: /usr/share/python3/dist
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/sudo$ cd /usr/share/python3/dist
hacker@commands~an-epic-filesystem-quest:/usr/share/python3/dist$ ls
README python3-cryptography python3-mako python3-six
hacker@commands~an-epic-filesystem-quest:/usr/share/python3/dist$ ls -a
. .. README python3-cryptography python3-mako python3-six
hacker@commands~an-epic-filesystem-quest:/usr/share/python3/dist$ ls -a
. .. README python3-cryptography python3-mako python3-six
hacker@commands~an-epic-filesystem-quest:/usr/share/python3/dist$ cat README
Yahaha, you found me!
The next clue is in: /usr/lib/python3/dist-packages/plumbum/cli/i18n/de/LC_MESSAGES

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/share/python3/dist$ ls /usr/lib/python3/dist-packages/plumbum/cli/i18n/de/LC_MESSAGES
ALERT-TRAPPED plumbum.cli.mo
hacker@commands~an-epic-filesystem-quest:/usr/share/python3/dist$ cat /usr/lib/python3/dist-packages/plumbum/cli/i18n/de/LC_MESSAGES/ALERT-TRAPPED
Lucky listing!
The next clue is in: /usr/share/perl/5.38.2/IO/Socket

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/share/python3/dist$ ls /usr/share/perl/5.38.2/IO/Socket
DISPATCH-TRAPPED IP.pm
hacker@commands~an-epic-filesystem-quest:/usr/share/python3/dist$ cat /usr/share/perl/5.38.2/IO/Socket/DISPATCH-TRAPPED
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{8g8NwwdHikkhJIxrSm2E-hR4YEN.QX5IDO0wyMwEzM2EzW}
