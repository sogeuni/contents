---
title: 4.1. Variable Substitution
---
The _name_ of a variable is a placeholder for its _value_, the data it holds. Referencing (retrieving) its value is called _variable substitution_.

## $

Let us carefully distinguish between the _name_ of a variable and its _value_. If **variable1** is the name of a variable, then **$variable1** is a reference to its _value_, the data item it contains. [^1]

```bash
bash$ variable1=23


bash$ echo variable1
variable1

bash$ echo $variable1
23
```

The only times a variable appears "naked" -- without the $ prefix -- is when declared or assigned, when _unset_, when [[internal#^EXPORTREF|exported]], in an arithmetic expression within [[double-parentheses-construct.html|double parentheses (( ... ))]], or in the special case of a variable representing a [[debugging#^SIGNALD|signal]] (see [[debugging#^EX76|Example 32-5]]). Assignment may be with an = (as in _var1=27_), in a [[internal#^READREF|read]] statement, and at the head of a loop (_for var2 in 1 2 3_).

Enclosing a referenced value in _double quotes_ (" ... ") does not interfere with variable substitution. This is called _partial quoting_, sometimes referred to as "weak quoting." Using single quotes (' ... ') causes the variable name to be used literally, and no substitution will take place. This is _full quoting_, sometimes referred to as 'strong quoting.' See [[Chapter 5. Quoting|Chapter 5]] for a detailed discussion.

Note that **$variable** is actually a simplified form of **${variable}**. In contexts where the **$variable** syntax causes an error, the longer form may work (see [[parameter-substitution.html|Section 10.2]], below).

**Example 4-1. Variable assignment and substitution**

```bash
#!/bin/bash
# ex9.sh

# Variables: assignment and substitution

a=375
hello=$a
#   ^ ^

#-------------------------------------------------------------------------
# No space permitted on either side of = sign when initializing variables.
# What happens if there is a space?

#  "VARIABLE =value"
#           ^
#% Script tries to run "VARIABLE" command with one argument, "=value".

#  "VARIABLE= value"
#            ^
#% Script tries to run "value" command with
#+ the environmental variable "VARIABLE" set to "".
#-------------------------------------------------------------------------


echo hello    # hello
# Not a variable reference, just the string "hello" ...

echo $hello   # 375
#    ^          This *is* a variable reference.
echo ${hello} # 375
#               Likewise a variable reference, as above.

# Quoting . . .
echo "$hello"    # 375
echo "${hello}"  # 375

echo

hello="A B  C   D"
echo $hello   # A B C D
echo "$hello" # A B  C   D
# As we see, echo $hello   and   echo "$hello"   give different results.
# =======================================
# Quoting a variable preserves whitespace.
# =======================================

echo

echo '$hello'  # $hello
#    ^      ^
#  Variable referencing disabled (escaped) by single quotes,
#+ which causes the "$" to be interpreted literally.

# Notice the effect of different types of quoting.


hello=    # Setting it to a null value.
echo "\$hello (null value) = $hello"      # $hello (null value) =
#  Note that setting a variable to a null value is not the same as
#+ unsetting it, although the end result is the same (see below).

# --------------------------------------------------------------

#  It is permissible to set multiple variables on the same line,
#+ if separated by white space.
#  Caution, this may reduce legibility, and may not be portable.

var1=21  var2=22  var3=$V3
echo
echo "var1=$var1   var2=$var2   var3=$var3"

# May cause problems with legacy versions of "sh" . . .

# --------------------------------------------------------------

echo; echo

numbers="one two three"
#           ^   ^
other_numbers="1 2 3"
#               ^ ^
#  If there is whitespace embedded within a variable,
#+ then quotes are necessary.
#  other_numbers=1 2 3                  # Gives an error message.
echo "numbers = $numbers"
echo "other_numbers = $other_numbers"   # other_numbers = 1 2 3
#  Escaping the whitespace also works.
mixed_bag=2\ ---\ Whatever
#           ^    ^ Space after escape (\).

echo "$mixed_bag"         # 2 --- Whatever

echo; echo

echo "uninitialized_variable = $uninitialized_variable"
# Uninitialized variable has null value (no value at all!).
uninitialized_variable=   #  Declaring, but not initializing it --
                          #+ same as setting it to a null value, as above.
echo "uninitialized_variable = $uninitialized_variable"
                          # It still has a null value.

uninitialized_variable=23       # Set it.
unset uninitialized_variable    # Unset it.
echo "uninitialized_variable = $uninitialized_variable"
                                # uninitialized_variable =
                                # It still has a null value.
echo

exit 0
```

> [!caution]
> An uninitialized variable has a "null" value -- no assigned value at all (_not_ zero!).
>
> ```bash
> if [ -z "$unassigned" ]
> then
>   echo "\$unassigned is NULL."
> fi     # $unassigned is NULL.
> ```
>
> Using a variable before assigning a value to it may cause problems. It is nevertheless possible to perform arithmetic operations on an uninitialized variable.
>
> ```bash
> echo "$uninitialized"                                # (blank line)
> let "uninitialized += 5"                             # Add 5 to it.
> echo "$uninitialized"                                # 5
> 
> #  Conclusion:
> #  An uninitialized variable has no value,
> #+ however it evaluates as 0 in an arithmetic operation.
> ```
>
> See also [[internal#^SELFSOURCE|Example 15-23]].

[^1]: Technically, the _name_ of a variable is called an _lvalue_, meaning that it appears on the _left_ side of an assignment statment, as in **VARIABLE=23**. A variable's _value_ is an _rvalue_, meaning that it appears on the _right_ side of an assignment statement, as in **VAR2=$VARIABLE**.

    A variable's _name_ is, in fact, a _reference_, a _pointer_ to the memory location(s) where the actual data associated with that variable is kept.
