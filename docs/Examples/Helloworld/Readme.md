---
title: "Example: Hello World"
---



# Hello world

A simple script outputting the famous "Hello World".

`helloworld.CiCIs:`

````CiCIscript
.tell{text:'Hello world';target:con;nl=1}
.end
````

## Breakdown

### [The dot](https://marnix0810.github.io/ASCCISL/Commands/dot/)

> The dot refers to internal command, these are the commands that are  always included in CiCI’s basis. Internal commands should always be  called using a dot and directly after the name of the command, without  any spaces or other tokens in between.

See: <https://marnix0810.github.io/ASCCISL/Commands/dot/>

### [tell](https://marnix0810.github.io/ASCCISL/Commands/dot/dottell)

> Tell is the internal command that outputs text, tell knows a couple of arguments.
>
> ###### text
>
> _text_ is the easiest part, it tells _tell_ what text to print. 
>
> ###### target
>
> _target_ accepts either `con`, a device-name to send the text string to, or a specific file path.
>
> **examples:**
>
> ````
> ,sends it to the console, which is default for most languages
> target:con;
> 
> ,sends it to lcdscreen1, if that lcd screen supports direct text input.
> target:lcdscreen1;
> 
> ,sends it to myfile.txt on the oompa drive
> target:'/MEDIA/mark/oompa/myfile.txt'
> ````
>
> ###### nl
>
> *nl* sets a newline, using a boolean value that contains either `1` or `0`, for true or false. The newline will always be printed before the text value. *.tell* without the *nl*-argument, will always fall back to it's standard value 1.
>
> Example:
>
>
> ```CiCIScript
> .tell{text:'Hello';target:con;nl=1}
> .tell{text:' world';target:con;nl=0}
> ```
>
> will output 
>
> ```text
> Hello world
> ```
>
> but
>
> ```CiCIScript
> .tell{text:'Hello';target:con;nl=1}
> .tell{text:' world';target:con;nl=0}
> ```
>
> will output 
>
> ```text
> Hello
> world
> ```
>
> Which is probably not the goal to achieve in this case.

See: <https://marnix0810.github.io/ASCCISL/Commands/dot/dottell>

### [end](https://marnix0810.github.io/ASCCISL/Commands/dot/dotend)

> `.end` is used at the end of scripts or routines to indicate the end of file is achieved, sometimes even when there's unused code ahead.
>
> [end is an internal command.](https://marnix0810.github.io/ASCCISL/Commands/dot/)

See: <https://marnix0810.github.io/ASCCISL/Commands/dot/dotend>
