# Difference between \$@ and \$*

When in double quotes:
* `"$@"` expands to `"$1" "$2" "$3" ...`
* `"$*"` expands to `"$1c$2c$3c..."` (where `c` is the first character
  in `IFS` or space)

When unquoted, they behave really the same in practical cases.
* Treat `$@` as an array of strings
* Treat `$*` as a single concatenated string

---

Consider the following script:

```bash
# bar.sh
echo "Arg 1: $1"
echo "Arg 2: $2"
echo "Arg 3: $3"
echo
```

and

```bash
# foo.sh
echo '$* without quotes:'
./bar.sh $*

echo '$@ without quotes:'
./bar.sh $@

echo '$* with quotes:'
./bar.sh "$*"

echo '$@ with quotes:'
./bar.sh "$@"
```

```
$ ./foo.sh arg1 "arg21 arg22" arg3
$* without quotes:            
Arg 1: arg1
Arg 2: arg21
Arg 3: arg22

$@ without quotes:
Arg 1: arg1
Arg 2: arg21
Arg 3: arg22

$* with quotes:
Arg 1: arg1 arg21 arg22 arg3
Arg 2:
Arg 3:

$@ with quotes:
Arg 1: arg1
Arg 2: arg21 arg22
Arg 3: arg3
```

---

* `"$*"` ignores quotes in the argument list,
* `"$*"` treats the whole argument list as a single concatenated string

and

* `"$@"` treats quoted arguments to be a single argument
* `"$@"` is an array of strings

Reference:

* `man bash`
* <https://stackoverflow.com/a/22589064/2827680>

Tags:

    #literature-note #scripting #syntax
