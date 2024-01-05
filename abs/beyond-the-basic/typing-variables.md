---
title: "9.2. Typing variables: **declare** or **typeset**"
---

The _declare_ or _typeset_ [[internal#^BUILTINREF|builtins]], which are exact synonyms, permit modifying the properties of variables. This is a very weak form of the _typing_ [^1] available in certain programming languages. The _declare_ command is specific to version 2 or later of Bash. The _typeset_ command also works in ksh scripts.

**declare/typeset options**

-r _readonly_

(**declare -r var1** works the same as **readonly var1**)

This is the rough equivalent of the **C** _const_ type qualifier. An attempt to change the value of a _readonly_ variable fails with an error message.

```bash
declare -r var1=1
echo "var1 = $var1"   # var1 = 1

(( var1++ ))          # x.sh: line 4: var1: readonly variable
```

-i _integer_

```bash
declare -i number
# The script will treat subsequent occurrences of "number" as an integer.		

number=3
echo "Number = $number"     # Number = 3

number=three
echo "Number = $number"     # Number = 0
# Tries to evaluate the string "three" as an integer.
```

Certain arithmetic operations are permitted for declared integer variables without the need for [[moreadv#^EXPRREF|expr]] or [[internal#^LETREF|let]].

```bash
n=6/3
echo "n = $n"       # n = 6/3

declare -i n
n=6/3
echo "n = $n"       # n = 2
```

-a _array_

```bash
declare -a indices
```

The variable _indices_ will be treated as an [[arrays#^ARRAYREF|array]].

-f _function(s)_

```bash
declare -f
```

A **declare -f** line with no arguments in a script causes a listing of all the [[functions#^FUNCTIONREF|functions]] previously defined in that script.

```bash
declare -f function_name
```

A **declare -f function_name** in a script lists just the function named.

-x [[internal#^EXPORTREF|export]]

```bash
declare -x var3
```

This declares a variable as available for exporting outside the environment of the script itself.

-x var=$value

```bash
declare -x var3=373
```

The **declare** command permits assigning a value to a variable in the same statement as setting its properties.

**Example 9-10. Using _declare_ to type variables**

```bash
#!/bin/bash

func1 ()
{
  echo This is a function.
}

declare -f        # Lists the function above.

echo

declare -i var1   # var1 is an integer.
var1=2367
echo "var1 declared as $var1"
var1=var1+1       # Integer declaration eliminates the need for 'let'.
echo "var1 incremented by 1 is $var1."
# Attempt to change variable declared as integer.
echo "Attempting to change var1 to floating point value, 2367.1."
var1=2367.1       # Results in error message, with no change to variable.
echo "var1 is still $var1"

echo

declare -r var2=13.36         # 'declare' permits setting a variable property
                              #+ and simultaneously assigning it a value.
echo "var2 declared as $var2" # Attempt to change readonly variable.
var2=13.37                    # Generates error message, and exit from script.

echo "var2 is still $var2"    # This line will not execute.

exit 0                        # Script will not exit here.
```

> [!caution]
> Using the _declare_ builtin restricts the [[subshells#^SCOPEREF|scope]] of a variable.
>
> ```bash
> foo ()
> {
> FOO="bar"
> }
> 
> bar ()
> {
> foo
> echo $FOO
> }
> 
> bar   # Prints bar.
> ```
>
> However . . .
>
> ```bash
> foo (){
> declare FOO="bar"
> }
> 
> bar ()
> {
> foo
> echo $FOO
> }
> 
> bar  # Prints nothing.
> 
> 
> # Thank you, Michael Iatrou, for pointing this out.
> ```

## 9.2.1. Another use for _declare_

The _declare_ command can be helpful in identifying variables, [[othertypesv#^ENVREF|environmental]] or otherwise. This can be especially useful with [[arrays#^ARRAYREF|arrays]].

```bash
bash$ declare | grep HOME
HOME=/home/bozo


bash$ zzy=68
bash$ declare | grep zzy
zzy=68


bash$ Colors=([0]="purple" [1]="reddish-orange" [2]="light green")
bash$ echo ${Colors[@]}
purple reddish-orange light green
bash$ declare | grep Colors
Colors=([0]="purple" [1]="reddish-orange" [2]="light green")
	     
```

[^1]: In this context, _typing_ a variable means to classify it and restrict its properties. For example, a variable _declared_ or _typed_ as an integer is no longer available for [[refcards#^STRINGOPSTAB|string operations]].

    ```bash
    declare -i intvar

    intvar=23
    echo "$intvar"   # 23
    intvar=stringval
    echo "$intvar"   # 0
    ```
