hacker@globbing~matching-with-:/challenge/files$ /challenge/run /challenge/files/[f]
Your expansion did not expand to the requested files (file*a, file_b, file_h,
and file_s). Instead, it expanded to:
/challenge/files/[f]
hacker@globbing~matching-with-:/challenge/files$ /challenge/run /challenge/files/file*[abhs]
Your expansion did not expand to the requested files (file*a, file_b, file_h,
and file_s). Instead, it expanded to:
/challenge/files/file_a /challenge/files/file_b /challenge/files/file_h /challenge/files/file_s
hacker@globbing~matching-with-:/challenge/files$ /challenge/run
Error: you did not use a square bracket glob...
hacker@globbing~matching-with-:/challenge/files$ ../run /file[absh]
Your expansion did not expand to the requested files (file_a, file_b, file_h,
and file_s). Instead, it expanded to:
/file[absh]
hacker@globbing~matching-with-:/challenge/files$ ../run file*[abhs]
You got it! Here is your flag!
pwn.college{ogsN-nwWXpV_NJbVxZT7mU8qp-4.QXzIDO0wyMwEzM2EzW}
