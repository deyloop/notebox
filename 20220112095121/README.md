# Adding filter capabilities to any Bash function

If you have a bash function that can transform lines taken as arguments, 
the following trick can be used to give that function line-filter or 
file-filter capabilities, depending on how the function treats newlines.


```bash
mylinefunc() {
  __line_filter "$@" && return $?

  # transform a single line of input
  echo "${1-#}" "$*"
}

__line_filter() {
  [[ -n "$1" ]] && return 1
  while IFS= read -ra args; do
    "${FUNCNAME[1]}" "${args[@]}"
  done
}
```

Explanation:

* All arguments are passed to `__line_filter` first. `__line_filter` 
  checks to see if arguments exist (if the length of `$1` is not zero). 

* If the argument list is not empty, the `__line_filter` function 
  returns so that the original function can process the arguments as 
  usual.

* If the argument list is empty, the `__line_filter` function takes 
  input from `stdin`, and calls the original function, passing each line 
  from `stdin` as a line of arguments.

  > `FUNCNAME` is somewhat of a call stack, so `FUNCNAME[1]` would 
  > evaluate to the name of the previous function in the stack


If the function can handle line newlines, use  `__file_filter` instead 
of `__line_filter`.

```bash
__file_filter() {
  [[ -n "$1" ]] && return 1
  "${FUNCNAME[1]}" "$(</dev/stdin)"
}
```


Related:

* CLI IO Schemes/Methods: <../20220112092321/README.md>
* Unix Filter IO Scheme: <../20220112093437/README.md>


References:

* What is a UNIX/Linux Filter? - rwxrob: <https://github.com/rwxrob/zet/blob/e2ab6dbfdc73d54d3aef1634fa659d29d609b1c1/20210809223847/README.md>
* `man bash`
* `help read`


Tags:

    #literature-note #unix #io #bash #scripting #bash-tricks
