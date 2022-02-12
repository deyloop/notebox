# Github: Close Issues from commit messages

You can use any of these keywords to close issue via commit message:

`close`, `closes`, `closed`, `fix`,`fixes`, `fixed`, `resolve`,
`resolves`, `resolved`

* Include in the commit message `<keyword> #<issue-id>`
* These keywords are case-insensitive
* Multiple issues can be closed at once, separate them by commas

    ```sh
    git commit -m "closes #1, fixed #2, closes #3"
    ```



---

References:

* GitHub: How can I close the two issues with commit message 
  <https://stackoverflow.com/questions/60027222/github-how-can-i-close-the-two-issues-with-commit-message>

* Linking a pull request to an issue - Github Docs
  <https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue>

---

    #literature-note #source-control #tools #conventions
