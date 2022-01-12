# CLI IO Schemes/Methods

An IO Scheme is the method in which Input is obtained, and Output is 
given back to the user. The scheme describes the rules and locations 
that the program/tool shall place/expect to take/put information.

A CLI (Command-line Interface) Tool has the following Input schemes 
available to it:

* Command-Line arguments
* Environment Variables
* from `stdin`
* local file or other IO device/file descriptor

For Output:
* to `stdout`
* local file or other IO device/file descriptor

Usually, `stdin` and `stdout` can be redirected to any file descriptor 
of choosing when invoking the tool, hence support of `stdin` and `stout` 
IO schemes is enough to support IO with any device/file.


