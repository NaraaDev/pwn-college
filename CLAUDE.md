# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

Personal notebook for [pwn.college](https://pwn.college) challenges. There is no code, build system, or test suite — each Markdown file is a transcript / solution log for one challenge, including the captured flag (`pwn.college{...}`).

## Structure

Top-level directories mirror pwn.college module names; one file per challenge:

- `Start-Here/` — onboarding challenges (SSH, GUI, terminal basics, the flag file).
- `Linux Luminarium/Hello Hackers/` — first commands, arguments, history.
- `Linux Luminarium/Pondering Paths/` — absolute vs. relative paths, `cd`, `$HOME`.
- `Comprehending Commands/` — `cat`, `ls`, `grep`, `touch`, `mv`, `rm`, file comparison.

Filenames intentionally use the human-readable challenge title (spaces, punctuation, occasional typos preserved from upstream). When editing or referencing them, always quote the path.

## File Conventions

Each challenge file is a pasted terminal session. Recurring pattern to preserve when adding new entries:

```
hacker@<module>~<challenge>:~$ <command>
<output>
...
pwn.college{<flag>}
```

- Keep the prompt line (`hacker@…:~$`) intact — it identifies which challenge the transcript belongs to.
- Flags are the deliverable; don't redact, summarize, or reformat them. They are unique per user and harmless outside pwn.college.
- Multi-level challenges (e.g. `Pondering Paths/Positino Elsewhere.md`) record every level in order; append new levels rather than rewriting.

## Workflow Notes

- No commands to build, lint, or test. Skip the usual TDD / code-review / build-fix loops — they don't apply.
- Commit style observed in `git log`: `feat: <module or challenge>` (e.g. `feat: pondering paths`, `feat: linux intro`). Match this style for new challenge captures.
- The repo is private notes; do not "fix" the typos in filenames (`Positino Elsewhere.md`, `Persistend Home Directories-Two`) — they are how the user filed them.
