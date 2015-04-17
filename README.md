git-squash
==========

Tool to squash the current branch/HEAD and rebase it onto a given commit.

Usage:

```
Usage: git squash [-m <commit msg>] [-a|--append] [-f|--full] <base>
  -m <commit msg>   Used to provide a new message for the squashed commit
  -a                If specified, the commit msg will be followed by all squashed commits informations
  -f|--full         If '-a|--append' is specified, all the messages will contain more informations (author, date...)
```

This calls `git rebase -i`, but automatically replaces all but the first
`pick` entry with `squash`.

If the rebase is trivial (e.g. `base` is an ancestor of the current `HEAD`) and
does not require interactive conflict resolution, `git squash` can also set
the commit message.

Requirements: `bash`, `awk`, `grep` with PCRE support, and of course
`git` >= 1.7.8, and a set `EDITOR` environment variable.

Installation: copy the git-squash file to a directory on your `PATH` and `chmod +x`.

Or execute this script:

```bash
sudo wget https://raw.githubusercontent.com/Pierstoval/git-squash/master/git-squash -O /usr/local/bin/git-squash
sudo chmod a+x /usr/local/bin/git-squash
```
