# Tab Completion for Bash Script Sub-Commands

Taking advantage of the [Programmable Tab Completion in Bash][1], Bash scripts that have subcommands can provide TAB completion in order to discover these subcommands in the following manner:

1. [Gather a list of subcommands dynamically][2], say in a list
   `COMMANDS`

1. Use the following code to give completion output

     ```bash
     if [[ -n $COMP_LINE  ]]; then
       line=${COMP_LINE#* }
       for c in "${COMMANDS[@]}"; do
         [[ ${c:0:${#line}} == "${line,,}" ]] && echo "$c"
       done
       exit
     fi
     ```

    Explaination:
    * Check to see if we are in Tab completion mode. Presence of `COMP_LINE` is
      an indication or this.
    * Get the current word we are typing.
    * Match the incomplete work with names of commands in `COMMANDS`
    * echo any sub-commands that match

1. Add `complete -C prog prog` to `~/.bashrc`, where `prog` is the program that
   the above completion code would be a part of.


[1]: ../20220113084600/README.md "Programmable Tab Completion in Bash"
[2]: ../20220114044631/README.md "20220114044631"


Related:
* [20220113084600](../20220113084600/README.md) Programmable Tab Completion in Bash 
* [20220114044631](../20220114044631/README.md) Bash Construct List of Sub-Commands

Reference:
* `man bash`
* @rwxrob's Bash Command Template: <https://github.com/rwxrob/template-bash-command>


Tags:

    #literature-note #scripting #tips
