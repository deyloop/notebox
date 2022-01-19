# Replace file with version from another branch

Merge conflicts can be annoying. Even if using `git merge --strategy
thiers branchname`, you can have weird misplaced hunks. 

If you want the current file to be replaced with the version from
another branch without questions, try

```sh
git checkout otherbranch -- filename
```

... while in the process of resolving merge conflicts between the current
branch and `otherbranch`. 

---

Reference:

* `man git-checkout`

Tags:

    #literature-note #git #source-control #workflow
