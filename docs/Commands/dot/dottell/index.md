---
title: Dot-tell
---



# tell

Tell is the [internal command](https://marnix0810.github.io/ASCCISL/Commands/dot/) that outputs text, tell knows a couple of arguments.

###### text

_text_ is the easiest part, it tells _tell_ what text to print. 

###### target

_target_ accepts either `con`, a device-name to send the text string to, or a specific file path.

**examples:**

````
,sends it to the console, which is default for most languages
target:con;

,sends it to lcdscreen1, if that lcd screen supports direct text input.
target:lcdscreen1;

,sends it to myfile.txt on the oompa drive
target:'/MEDIA/mark/oompa/myfile.txt'
````

###### nl

*nl* sets a newline, using a boolean value that contains either `1` or `0`, for true or false. The newline will always be printed before the text value. *.tell* without the *nl*-argument, will always fall back to it's standard value 1.

Example:


```CiCIScript
.tell{text:'Hello';target:con;nl=1}
.tell{text:' world';target:con;nl=0}
```

will output 

```text
Hello world
```

but

```CiCIScript
.tell{text:'Hello';target:con;nl=1}
.tell{text:' world';target:con;nl=0}
```

will output 

```text
Hello
 world
```

Which is probably not the goal to achieve in this case.