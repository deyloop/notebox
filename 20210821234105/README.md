# Order of Startup Files for `bash`

The following table shows what files are sourced by `bash` depending on how it
was invoked. Order is top to bottom, `x` meaning not sourced, `yes` meaning
sourced.

|.                |...|L..|.I.|LI.|..S|L.S|.IS|LIS|comments                                                       |
|-----------------|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|---------------------------------------------------------------|
|`/etc/profile`   |x  |yes|x  |yes|x  |yes|x  |yes|-                                                              |
|`~/.bash_profile`|x  |yes|x  |yes|x  |x  |x  |x  |-                                                              |
|`~/.bash_login`  |x  |yes|x  |yes|x  |x  |x  |x  |only if `~/.bash_profile` is not found                         |
|`~./profile`     |x  |yes|x  |yes|x  |yes|x  |yes|only if none of `~/.bash_profile` and `~./bash_login` are found|
|`~/.bashrc`      |yes|yes|yes|yes|x  |x  |x  |x  |-                                                              |
|`BASHENV`        |yes|yes|x  |x  |x  |x  |x  |x  |`BASHENV` cannot use `PATH` while expansion                    |
|`ENV `           |x  |x  |x  |x  |x  |x  |yes|yes|`ENV` cannot use `PATH` while expansion                        |
|`~/.bash_logout` |x  |yes|x  |yes|x  |x  |x  |x  |only when exiting                                              |

`L` means *login-shell*, `I` means *interactive shell* and `S` means *stared as
`sh`*. So, `L..` means non-interactive Login-shell normally run, `.I.` means
non-login Interactive shell. `LIS` means Login-interactive shell in POSIX mode.

**Do remember**: Environment variables that are `export`ed will be passed to
any subshells, so subshells get any environment variables created in their
parent shell even if the subshell does not source the file where the
environment variable was defined.

#### References

- [`bash` man page](https://www.man7.org/linux/man-pages/man1/bash.1.html) in section `INVOCATION`
