# SSH bash session is not login shell

This means that it will not source the following config files that are normally sourced when running bash as a login interactive shell.

* `/etc/profile`
* `~/.bash_profile`
* `~/.bash_login`
* `~/.profile`

A bash session started as a consequence of logging into a remote machine using SSH will only source `~/.bashrc` and no other files. So don't be surprised.

Related

* [Order of Startup Files for `bash`](../20210821234105/README.md)
