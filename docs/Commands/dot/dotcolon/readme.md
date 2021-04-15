# :

The colon sets variables, these are standard saved as a string, but if containing a number they will be able to be altered. **The colon is an internal command.**



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

String variables are written to a temporary file (`(temp folder)/CiCISessions/(session).tmp/vars/(varname).cicivar`) until being called and then erased from RAM as soon as they seem unused.

For numbers (and automatically 0/1 booleans too), there's more.

###### Using permactive variables using .:#

Although a number containing string can be sent to any command that supports numbers, sometimes a number might look like a string for the computer.

A full number can be set like `.: number=20` and CiCI will automatically save it as a number.  `.: number=2,0` , though, can be problematic. There's a solution for both!



>  In programming languages, numbers are typically split into 32-bit numbers, and 64-bit numbers. In Batch, you had to evoke PowerShell to be able to use 64-bit numbers. And in JAVA the variables of numbers and of what it calls '`doubles`'  are two entirely different things. 32-bit numbers and 64-bit numbers.
>
>  In CiCI, variables are not saved in ram, but put directly into a temporary file (`(temp folder)/CiCISessions/(session).tmp/vars/(varname).cicivar`).
>
>  This might slow down CiCIscripts a lot, especially in case of number variables. And that's where .:# comes in. It defines a number, not a string. Even though it won't change the way the variable can be called it does make CiCI aware that is a number that needs to be in the RAM, and CiCI will have to figure out what type of number it is.



`.:#` defines a variable, to save it to the RAM instead of to the temp folder. Permactive variables can only contain numbers, which makes them usefull to calculate with.

```
.: num=1
.: num+=3
.tell{text:%num%;target:con;nl=0}
```

and

```
.:# num=1
.:# num+=3
.tell{text:%num%;target:con;nl=0}
```

Would both output `4`. But the latter would be able to do so at a much higher speed, especially on a hard drive.

To permactivate a set variable, just use  `.:# var`. To put a variable to stand-bye (the usual state, and the standard state for strings), `.: # var` will do.

Altering an permactive variable with plain `.:` will stand-bye it too, since it just saves it differently, the contrary is not possible, for `.:#` needs to be sure it sets numbers.