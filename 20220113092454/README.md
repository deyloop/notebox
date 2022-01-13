# Tab Completion for Bash Script Sub-Commands

Taking advantage of the [Programmable Tab Completion in Bash][1], Bash scripts that have subcommands can provide TAB completion in order to discover these subcommands in the following manner:

1. Follow a special character delimited naming convention for Bash functions
   that represent a subcommand. For example, they can follow the
   `x.subcommandA`.

   That is, starting sub command function names with an x, followed by a `.` and then the subcommand name, `subcommandA` in the above example

1. Use the following code to gather a list of all sub-commands dynamically:
   
    ```bash
    # Obtain all subcommands
    while IFS= read -r line; do
      [[ $line =~ ^declare\ -f\ x\. ]] || continue 
      COMMANDS+=( "${line##declare -f x.}" )
    done < <(declare -F)
    mapfile -t COMMANDS < <(LC_COLLATE=C sort < <(printf "%s\n" "${COMMANDS[@]}"))
    ```

    Explaination:
    * `declare -F` will produce a newline delimited list of all Bash functions declared.
    * Functions that do not follow the naming convention specified above are ignored.
    * The functions that do follow the convention are added to `COMMANDS`
    * The function names are sorted and put into `COMMANDS`

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


Related:
* [20220113084600](../20220113084600/README.md) Programmable Tab Completion in Bash 


Reference:
* `man bash`
* @rwxrob's Bash Command Template: <https://github.com/rwxrob/template-bash-command>


Tags:

    #literature-note #scripting #tips
