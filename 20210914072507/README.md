# Sign git commits with GPG

Signing git commits give members of the team you are working with and others depending on the software you write the confidence that the code being committed is indeed written by you and not an imposter.

After [Creating a GPG key pair][1], `git` can be configured to use the generated key to sign commits and tags, like this:

```sh
git config --global user.signingkey <key-id>
```

Where `<key-id>` must be the id of the key being used.

After this, there are three ways to make git sign commits:
1. Add the `-S` flag on the commits you want to sign:
   ```sh
   git commit -a -S -m "Commit Message, That is signed"
   ```
1. Configure `git` to sign all commits automatically for a particular repo
   ```sh
   cd path/to/repo/needing/auto/signs
   git config commit.gpgsign true
   ```
1. Configure `git` to sign all commits on all repos
   ```sh
   git config --global commit.gpgsign true
   ```
Adding the key to the remote repo host (Github, Gitlab) is also recomended.

References:
* <https://stackoverflow.com/questions/10161198/is-there-a-way-to-autosign-commits-in-git-with-a-gpg-key>
* <https://git-scm.com/book/en/v2/Git-Tools-Signing-Your-Work>


   


