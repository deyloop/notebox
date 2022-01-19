# Maintain a local `git` Repository, Even if the rest of your Team does not

When working in a collaborative project where part of your team is
either not familiar with Version Control Systems like `git` or they
refuse to use such tools for some reason, it can be a hassle to
incorporate changes made by other team members into the copy of files
that you are working on. 

Maintaining a `git` repository of the files at your end helps in
collaboration even in this case.

I use the following set of branches:
* `upstream` - upstream changes are added here. This branch's history
  will reflect just the upstream changes, which is sometimes useful.
* `integration/clean` - This branch is where I clean and reformat the
  files received from upstream. Kind of like a merging point of the
  upstream files and the files I am working with.
* `integration/IO` - This is the branch that will contain my changes.
  Name this what you want.
* `main` - stable branch to contain tagged releases.

When upstream changes are to be merged with your local version, which
may have your own changes made locally, you can 

1. Add the upstream changes to `upstream` via copy paste, commit
1. Switch to `integration/clean`, then merge `upstream` into the current
   branch. (I prefer using a `--no-ff` merge to keep histories
   separate.) 
   
   - If a merge is messy, you can also replace a file on the current
     branch with a version from the `upstream` branch completely without
     questions using

       ```sh
       git checkout upstream -- <filename>
       ```
   * You can also open up a diff for the file you are editing against
     the same file from a different branch (like `integration/IO` to
     refer to your own additions) by using 

      ```sh
      git difftool integration/IO -- <filename>
      ```

     You can edit the file (the right side would be current branch) in
     the diff iteself, if using vim, and save it, even if its opened in
     read-only mode.

     Commit when satified

1. Switch to `integration/IO` and merge from `integration/clean` (again,
   `--no-ff` for separate histories). You can now add your own changes
   here.

   Commit when satisfied

1. Switch to `main`, merge from `integration/IO`, add a tag.

---

Related:

* [20220119070922](../20220119070922/README.md) Compare versions of file from Different Branches
* [20220119071757](../20220119071757/README.md) Replace file with version from another branch

Tags:

    #permanent-note #version-control #collaboration #team-work
