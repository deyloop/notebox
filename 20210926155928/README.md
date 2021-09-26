# `git add --patch`

I liked how `magit`, the git porcelain that comes with `emacs`, allowed you to
select what hunks to commit inside each file.

This is helpful if while making changes you make many separate unrelated
changes in the same file and want these separate changes to be in separate
commits. 

Turns out, plain `git` can do that too, with the `git add --patch` option. It
interactively goes through each **hunk** (a part of a file that has been
changed) and asks you if you want it to be staged. 
