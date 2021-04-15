---
title: Dot-llet
---



# llet

llet is the [internal command](https://asccisl-org.github.io/docs/Commands/dot/) that imports text to variables, llet knows a couple of arguments.

*llet* is the exact opposite of *tell*, their names mirror that.



## Arguments

llet knows three arguments.

.llet{source:(source);target:(variable);[line:(line)]}

| argument | meaning                                                      |
| -------- | ------------------------------------------------------------ |
| source   | The source tells _llett_ what the text to import should come from. It accepts either `con`, or a specific file path. *llet* only supports plain text. |
| target   | The variable name to sent the imported string to.            |
| line     | if _source_ contains a file path, _line_ is used to determine what line to import. If _line_ is not set, the first line of the file will be used. |


