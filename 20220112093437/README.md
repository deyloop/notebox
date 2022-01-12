# Unix Filter IO Scheme

A *filter* is a command that accepts input from `stdin`, transforms it 
in some way and outputs the transformed contents into `stdout`.

* Filters are very easy to compose into UNIX pipelines.
* Extremely handy when editing text in a text editor that allows 
  selecting text, running it through a filter and replacing the selected 
  text with the output. (`vi` and `vim`, even `emacs`, etc)

Filters are of two types:

* Line filters - program transforms the input line by line
* File filters - program transforms the whole input received via `stdin` 
  at once

Related:

* Unix Filter IO Scheme <../20220112093437/README.md>
* What is a UNIX/Linux Filter - by rwxrob: <https://github.com/rwxrob/zet/blob/e2ab6dbfdc73d54d3aef1634fa659d29d609b1c1/20210809223847/README.md>


Tags:

    #literature-note #unix #cli
