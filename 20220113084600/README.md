# Programmable Tab Completion in Bash

Bash Shell's Tab Completion can be programmed and used to provide TAB
completion for any cli program that you write, given that the your program is
able to read in environment variables.

Bash has the `complete` builtin that can be used to specify how TAB completion
must be performed when invoking a particular command. There are multiple ways
a so called `compspec` (Completion Specification) can be specified using the
`complete` builtin, but the most flexible in my opinion is by using the `-C`
flag.

```sh
complete -C command name
```

* `name` is the name of the program the completion specification is for.
* `command` is the name of a function or program that will provide the
  completion output.

When TAB is pressed while entering the arguments to `name`, the partially typed
arguments are put in and environment variable called `COMP_LINE`, along with
several other completion related variables:
 
* COMP_CWORD: An index into \${COMP_WORDS} of the word containing the current
  cursor posi‐ tion.  This variable is available only in shell functions
  invoked  by  the programmable completion facilities (see Programmable
  Completion below).
       
* COMP_KEY: The key (or final key of a key sequence) used to invoke the current
  comple‐ tion function.

* COMP_LINE: The current command line.  This variable is available only in
  shell  func‐ tions  and external commands invoked by the programmable
  completion facili‐ ties (see Programmable Completion below).

* COMP_POINT: The index of the current cursor position relative to the beginning
  of  the current  command.  If the current cursor position is at the end of
  the cur‐ rent command, the value of this variable is equal to  \${#COMP_LINE}.
  This variable is available only in shell functions and external commands
  invoked by the programmable completion facilities (see Programmable
  Completion  be‐ low).

* COMP_TYPE: Set  to  an integer value corresponding to the type of completion
  attempted that caused a completion function to be called: TAB, for normal
  completion, ?,  for  listing completions after successive tabs, !, for
  listing alterna‐ tives on partial word completion, @, to list completions if
  the word is not unmodified,  or %, for menu completion.  This variable is
  available only in shell functions and external commands invoked by the
  programmable  comple‐ tion facilities (see Programmable Completion below).

* COMP_WORDBREAKS: The  set  of characters that the readline library treats as
  word separators when performing word completion.  If COMP_WORDBREAKS is
  unset, it loses its special properties, even if it is subsequently reset.

* COMP_WORDS: An  array variable (see Arrays below) consisting of the individual
  words in the current command line.  The line is split into words as  readline
  would split  it,  using  COMP_WORDBREAKS  as  described  above.  This
  variable is available only in shell functions invoked by  the  programmable
  completion facilities (see Programmable Completion below).

From `man bash`:

> ... any shell function or command specified with the -F and -C options is invoked.
> When the command or function  is  invoked, the  COMP_LINE,  COMP_POINT,
> COMP_KEY, and COMP_TYPE variables are assigned values as described above under
> Shell Variables.  If a shell function is  being  invoked, the  COMP_WORDS  and
> COMP_CWORD variables are also set.  When the function or command is invoked,
> the first argument (\$1) is the name of the  command  whose  arguments  are
> being completed, the second argument (\$2) is the word being completed, and the
> third argument (\$3) is the word preceding the word being completed on  the
> current  command line.  No filtering of the generated completions against the
> word being completed is performed; the function or command has complete freedom
> in generating the matches.


The `command` can read these environment variables to output a list of newline delimited completion candidates to `stdout`.


References:

* `man bash`
* `help complete`


Tags:

    #literature-note #scripting #programming
