# CiCIScript / AS<font color="#13D3BD">CCIS</font>L

_**A**daptive **S**imple **<font color="#13D3BD">C</font>**ompatible **<font color="#13D3BD">C</font>**ommand **<font color="#13D3BD">I</font>**nterpreted **<font color="#13D3BD">S</font>**cripting **L**anguage designed to easily make the simplest of programs without the hassle of real programming languages._

By Marnix Bloeiman

also see: Marnix0810/MAASL-scriptinglanguage

## Introduction

Since this project is a retry/restart of MAASL, I think it has also become clear that I haven't been in the programming world lately. This is probably my last concept to turn into a project. And on top of that, this project is the first (well, MAASL is basically this project, but with a different approach.) started with the goal to make something that isn't just a tool, and something that I knew how to create. I truly have no idea on how to build an interpreter for it.

## My experience and motivation

In the past, as you can see, I have mainly wrote Batch. Batch is not a programming language, but called parts of code that I wrote in other languages. Unfortunately I'm not the best programmer, so I could not write a full program in a civilised programming language.

I do know a bit JAVA, VBScript, Rust and Python, especially my recent encounters of JAVA have re-inspired me to write this, because of the whole project, this README.MD file will be the core. Instead of writing code and explaining it afterwards, this project will first have an explanation of what has to happen, and the code afterwards.

## CiCIscript examples

To have a better view of what I am trying to accomplish I'll mainly write some CiCIscripts and explain what they do, and as I wrote before, I will try and code the interpreter around it. (Yes, help is always appreciated, with my level of motivation this project will take ages.)

### Hello world

A simple script outputting the famous "Hello World".

`helloworld.CiCIs:`

````CiCIscript
.tell{text:'Hello world';target:con;nl=1}
.end
````

#### Breakdown

##### .

The dot refers to internal command, these are the commands that are always included in CiCI's basis. Internal commands should always be called using a dot and directly after the name of the command, without any spaces or other tokens in between.

##### tell

Tell is the internal command that outputs text, tell knows a couple of arguments.

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
target:'/MEDIA/user/oompa/myfile.txt'
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
 world"
```
Which is probably not the goal to achieve in this case.

### Hello world 2

A simple script outputting the famous "Hello World", but with your name in it too.

`helloworld2.CiCIs:`

````CiCIscript
.: name=Mark
.tell{text:'Hello world, %name%';target:con;nl=1}
.end
````

#### Breakdown

##### .

The dot refers to internal command, these are the commands that are always included in CiCI's basis. Internal commands should always be called using a dot and directly after the name of the command, without any spaces or other tokens in between.

##### :

The double dot set variables, these are standard saved as a string, but if containing a number they will be able to be altered.

###### Setting variables using :

Some examples.

For a single word variable, use

```
.: word=single
```

for a string, the same logics can be used.

```
.: sentence="hi I am not single, I am with nine."
```



For numbers, theres more.

Although a number containing string can be sent to any command that supports numbers, sometimes a number might look like a string for the computer.

A full number can be set like `.: number=20` and CiCI will automatically save it as a number.  `.: number=2,0` , though, can be problematic. There's a solution for both!



>  In programming languages, numbers are typically split into 32-bit numbers, and 64-bit numbers. 

> In Batch, you had to evoke PowerShell to be able to use 64-bit numbers. And in JAVA the variables of numbers and of what it calls '`doubles`' 