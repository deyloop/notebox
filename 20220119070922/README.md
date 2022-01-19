# Compare versions of file from Different Branches

Say you have a file `filename` on branches `branch1` and `branch2`.

Say you are on `branch1`, and you want a side-by-side comparison of
`filename` between the two branches.

Here is the command:

```sh
git difftool branch2 -- filename
```

This will show the version from `branch2` on the left, and the version
from `branch1` on the right.

If your `difftool` is `vim`, you can make edits on the `branch1`
version, and save using `:w`, even if its initially opened in read-only
mode.

---

References:

* `man git-diff`
* `man git-difftool`

Tags

    #literature-note #workflow #tip #source-control
