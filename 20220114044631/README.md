# Bash Construct List of Sub-Commands

A bash script can have subcommands, like many cli tool have.

```sh
git clone git@github.com/deyloop/notebox
```

`clone` is a subcommand of the `git` cli.

---

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

Related:

* [20220113084600](../20220113084600/README.md) Programmable Tab Completion in Bash
* [20220113092454](../20220113092454/README.md) Tab Completion for Bash
  Script Sub-Commands

Reference:
* `man bash`
* @rwxrob's Bash Command Template: <https://github.com/rwxrob/template-bash-command>


Tags:

    #literature-note #snippet #scripting #tip
