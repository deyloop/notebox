# Bash Case Statement

* A branching/control-flow mechanism in Bash
* Execute Commands based on what pattern an expression matches.

```sh
case EXPRESSION in
  PATTERN1) COMMANDS ;;
  PATTERN2) COMMANDS ;;
  PATTERN3) COMMANDS ;;
  ...
esac
```

* Patterns are *shell patterns*, **not** Regular Expressions.
* Matching is done *top to bottom* and matching stops after the first
  match.

Related:

* [20220114052639](../20220114052639/README.md) Shell Pattern Matching


Reference:

* `man bash`


Tags:

    #literature-note #scripting #syntax
