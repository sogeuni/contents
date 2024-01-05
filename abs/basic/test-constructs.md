---
title: 7.1. Test Constructs
---

- An **if/then** construct tests whether the [[exit-status#^EXITSTATUSREF|exit status]] of a list of commands is 0 (since 0 means "success" by UNIX convention), and if so, executes one or more commands.
- There exists a dedicated command called **[[special-characters#^LEFTBRACKET|** ([left bracket]] special character). It is a synonym for **test**, and a [[internal#^BUILTINREF|builtin]] for efficiency reasons. This command considers its arguments as comparison expressions or file tests and returns an exit status corresponding to the result of the comparison (0 for true, 1 for false).
- With version 2.02, Bash introduced the [[test-constructs#^DBLBRACKETS|[[ ... ]]]] _extended test command_, which performs comparisons in a manner more familiar to programmers from other languages. Note that **[[internal#^KEYWORDREF|[** is a [keyword]], not a command.
    Bash sees **[[ $a -lt $b ]]** as a single element, which returns an exit status.
- The [[double-parentheses-construct.html|(( ... ))]] and [[internal#^LETREF|let ...]] constructs return an [[exit-status#^EXITSTATUSREF|exit status]], _according to whether the arithmetic expressions they evaluate expand to a non-zero value_. These [[Chapter 13. Arithmetic Expansion#^ARITHEXPREF|arithmetic-expansion]] constructs may therefore be used to perform [[other-comparison-operators#^ICOMPARISON1|arithmetic comparisons]].

```bash
(( 0 && 1 ))                 # Logical AND
echo $?     # 1     ***
# And so ...
let "num = (( 0 && 1 ))"
echo $num   # 0
# But ...
let "num = (( 0 && 1 ))"
echo $?     # 1     ***


(( 200 || 11 ))              # Logical OR
echo $?     # 0     ***
# ...
let "num = (( 200 || 11 ))"
echo $num   # 1
let "num = (( 200 || 11 ))"
echo $?     # 0     ***


(( 200 | 11 ))               # Bitwise OR
echo $?                      # 0     ***
# ...
let "num = (( 200 | 11 ))"
echo $num                    # 203
let "num = (( 200 | 11 ))"
echo $?                      # 0     ***

# The "let" construct returns the same exit status
#+ as the double-parentheses arithmetic expansion.
```

> [!caution]
> Again, note that the _exit status_ of an arithmetic expression is _not_ an error value.
>
> ```bash
> var=-2 && (( var+=2 ))
> echo $?                   # 1
> 
> var=-2 && (( var+=2 )) && echo $var
>                           # Will not echo $var!
> ```

- An **if** can test any command, not just conditions enclosed within brackets.

```bash
if cmp a b &> /dev/null  # Suppress output.
then echo "Files a and b are identical."
else echo "Files a and b differ."
fi

# The very useful "if-grep" construct:
# ----------------------------------- 
if grep -q Bash file
  then echo "File contains at least one occurrence of Bash."
fi

word=Linux
letter_sequence=inu
if echo "$word" | grep -q "$letter_sequence"
# The "-q" option to grep suppresses output.
then
  echo "$letter_sequence found in $word"
else
  echo "$letter_sequence not found in $word"
fi


if COMMAND_WHOSE_EXIT_STATUS_IS_0_UNLESS_ERROR_OCCURRED
  then echo "Command succeeded."
  else echo "Command failed."
fi
```

- _These last two examples courtesy of Stéphane Chazelas._

**Example 7-1. What is truth?**

```bash

#!/bin/bash

#  Tip:
#  If you're unsure how a certain condition might evaluate,
#+ test it in an if-test.

echo

echo "Testing \"0\""
if [ 0 ]      # zero
then
  echo "0 is true."
else          # Or else ...
  echo "0 is false."
fi            # 0 is true.

echo

echo "Testing \"1\""
if [ 1 ]      # one
then
  echo "1 is true."
else
  echo "1 is false."
fi            # 1 is true.

echo

echo "Testing \"-1\""
if [ -1 ]     # minus one
then
  echo "-1 is true."
else
  echo "-1 is false."
fi            # -1 is true.

echo

echo "Testing \"NULL\""
if [ ]        # NULL (empty condition)
then
  echo "NULL is true."
else
  echo "NULL is false."
fi            # NULL is false.

echo

echo "Testing \"xyz\""
if [ xyz ]    # string
then
  echo "Random string is true."
else
  echo "Random string is false."
fi            # Random string is true.

echo

echo "Testing \"\$xyz\""
if [ $xyz ]   # Tests if $xyz is null, but...
              # it's only an uninitialized variable.
then
  echo "Uninitialized variable is true."
else
  echo "Uninitialized variable is false."
fi            # Uninitialized variable is false.

echo

echo "Testing \"-n \$xyz\""
if [ -n "$xyz" ]            # More pedantically correct.
then
  echo "Uninitialized variable is true."
else
  echo "Uninitialized variable is false."
fi            # Uninitialized variable is false.

echo


xyz=          # Initialized, but set to null value.

echo "Testing \"-n \$xyz\""
if [ -n "$xyz" ]
then
  echo "Null variable is true."
else
  echo "Null variable is false."
fi            # Null variable is false.


echo


# When is "false" true?

echo "Testing \"false\""
if [ "false" ]              #  It seems that "false" is just a string ...
then
  echo "\"false\" is true." #+ and it tests true.
else
  echo "\"false\" is false."
fi            # "false" is true.

echo

echo "Testing \"\$false\""  # Again, uninitialized variable.
if [ "$false" ]
then
  echo "\"\$false\" is true."
else
  echo "\"\$false\" is false."
fi            # "$false" is false.
              # Now, we get the expected result.

#  What would happen if we tested the uninitialized variable "$true"?

echo

exit 0
```

**Exercise.** Explain the behavior of [[test-constructs#^EX10|Example 7-1]], above.

```bash
if [ condition-true ]
then
   command 1
   command 2
   ...
else  # Or else ...
      # Adds default code block executing if original condition tests false.
   command 3
   command 4
   ...
fi
```

> [!note] 
> When _if_ and _then_ are on same line in a condition test, a semicolon must terminate the _if_ statement. Both _if_ and _then_ are [[internal#^KEYWORDREF|keywords]]. Keywords (or commands) begin statements, and before a new statement on the same line begins, the old one must terminate.
>
> ```bash
> if [ -x "$filename" ]; then
> ```

**Else if and elif**

elif

**elif** is a contraction for _else if_. The effect is to nest an inner if/then construct within an outer one.

```bash
if [ condition1 ]
then
   command1
   command2
   command3
elif [ condition2 ]
# Same as else if
then
   command4
   command5
else
   default-command
fi
```

The **if test condition-true** construct is the exact equivalent of **if [ condition-true ]**. As it happens, the left bracket, **[** , is a _token_ [^1] which invokes the **test** command. The closing right bracket, **]** , in an if/test should not therefore be strictly necessary, however newer versions of Bash require it.

> [!note] 
> The **test** command is a Bash [[internal#^BUILTINREF|builtin]] which tests file types and compares strings. Therefore, in a Bash script, **test** does _not_ call the external /usr/bin/test binary, which is part of the _sh-utils_ package. Likewise, **[** does not call /usr/bin/[, which is linked to /usr/bin/test.
>
> ```bash
> bash$ type test
> test is a shell builtin
> bash$ type '['
> [ is a shell builtin
> bash$ type '[['
> [[ is a shell keyword
> bash$ type ']]'
> ]] is a shell keyword
> bash$ type ']'
> bash: type: ]: not found
> 	      
> ```
>
> If, for some reason, you wish to use /usr/bin/test in a Bash script, then specify it by full pathname.|

**Example 7-2. Equivalence of _test_, /usr/bin/test, [ ], and /usr/bin/[**

```bash
#!/bin/bash

echo

if test -z "$1"
then
  echo "No command-line arguments."
else
  echo "First command-line argument is $1."
fi

echo

if /usr/bin/test -z "$1"      # Equivalent to "test" builtin.
#  ^^^^^^^^^^^^^              # Specifying full pathname.
then
  echo "No command-line arguments."
else
  echo "First command-line argument is $1."
fi

echo

if [ -z "$1" ]                # Functionally identical to above code blocks.
#   if [ -z "$1"                should work, but...
#+  Bash responds to a missing close-bracket with an error message.
then
  echo "No command-line arguments."
else
  echo "First command-line argument is $1."
fi

echo


if /usr/bin/[ -z "$1" ]       # Again, functionally identical to above.
# if /usr/bin/[ -z "$1"       # Works, but gives an error message.
#                             # Note:
#                               This has been fixed in Bash, version 3.x.
then
  echo "No command-line arguments."
else
  echo "First command-line argument is $1."
fi

echo

exit 0
```

> The [[ ]] construct is the more versatile Bash version of [ ]. This is the _extended test command_, adopted from _ksh88_.
>
> No filename expansion or word splitting takes place between [[ and ]], but there is parameter expansion and command substitution.
>
> ```bash
> file=/etc/passwd
> 
> if [[ -e $file ]]
> then
>   echo "Password file exists."
> fi
> ```
>
> Using the **[[ ... ]]** test construct, rather than **[ ... ]** can prevent many logic errors in scripts. For example, the &&, \|, <, and > operators work within a [[ ]] test, despite giving an error within a [ ] construct.
>
> _Arithmetic evaluation_ of octal / hexadecimal constants takes place automatically within a [[ ... ]] construct.
>
> ```bash
> # [[ Octal and hexadecimal evaluation ]]
> # Thank you, Moritz Gronbach, for pointing this out.
> 
> 
> decimal=15
> octal=017   # = 15 (decimal)
> hex=0x0f    # = 15 (decimal)
> 
> if [ "$decimal" -eq "$octal" ]
> then
>   echo "$decimal equals $octal"
> else
>   echo "$decimal is not equal to $octal"       # 15 is not equal to 017
> fi      # Doesn't evaluate within [ single brackets ]!
> 
> 
> if [[ "$decimal" -eq "$octal" ]]
> then
>   echo "$decimal equals $octal"                # 15 equals 017
> else
>   echo "$decimal is not equal to $octal"
> fi      # Evaluates within [[ double brackets ]]!
> 
> if [[ "$decimal" -eq "$hex" ]]
> then
>   echo "$decimal equals $hex"                  # 15 equals 0x0f
> else
>   echo "$decimal is not equal to $hex"
> fi      # [[ $hexadecimal ]] also evaluates!
> ```

> [!note]
> Following an **if**, neither the **test** command nor the test brackets ( [ ] or [[ ]] ) are strictly necessary.
>
> ```bash
> dir=/home/bozo
> 
> if cd "$dir" 2>/dev/null; then   # "2>/dev/null" hides error message.
>   echo "Now in $dir."
> else
>   echo "Can't change to $dir."
> fi
> ```
>
> The "if COMMAND" construct returns the exit status of COMMAND.
>
> Similarly, a condition within test brackets may stand alone without an **if**, when used in combination with a [[list-cons#^LISTCONSREF|list construct]].
>
> ```bash
> var1=20
> var2=22
> [ "$var1" -ne "$var2" ] && echo "$var1 is not equal to $var2"
> 
> home=/home/bozo
> [ -d "$home" ] || echo "$home directory does not exist."
> ```

The [[double-parentheses-construct|(( )) construct]] expands and evaluates an arithmetic expression. If the expression evaluates as zero, it returns an [[exit-status#^EXITSTATUSREF|exit status]] of 1, or "false". A non-zero expression returns an exit status of 0, or "true". This is in marked contrast to using the **test** and [ ] constructs previously discussed.

**Example 7-3. Arithmetic Tests using (( ))**

```bash
#!/bin/bash
# arith-tests.sh
# Arithmetic tests.

# The (( ... )) construct evaluates and tests numerical expressions.
# Exit status opposite from [ ... ] construct!

(( 0 ))
echo "Exit status of \"(( 0 ))\" is $?."         # 1

(( 1 ))
echo "Exit status of \"(( 1 ))\" is $?."         # 0

(( 5 > 4 ))                                      # true
echo "Exit status of \"(( 5 > 4 ))\" is $?."     # 0

(( 5 > 9 ))                                      # false
echo "Exit status of \"(( 5 > 9 ))\" is $?."     # 1

(( 5 == 5 ))                                     # true
echo "Exit status of \"(( 5 == 5 ))\" is $?."    # 0
# (( 5 = 5 ))  gives an error message.

(( 5 - 5 ))                                      # 0
echo "Exit status of \"(( 5 - 5 ))\" is $?."     # 1

(( 5 / 4 ))                                      # Division o.k.
echo "Exit status of \"(( 5 / 4 ))\" is $?."     # 0

(( 1 / 2 ))                                      # Division result < 1.
echo "Exit status of \"(( 1 / 2 ))\" is $?."     # Rounded off to 0.
                                                 # 1

(( 1 / 0 )) 2>/dev/null                          # Illegal division by 0.
#           ^^^^^^^^^^^
echo "Exit status of \"(( 1 / 0 ))\" is $?."     # 1

# What effect does the "2>/dev/null" have?
# What would happen if it were removed?
# Try removing it, then rerunning the script.

# ======================================= #

# (( ... )) also useful in an if-then test.

var1=5
var2=4

if (( var1 > var2 ))
then #^      ^      Note: Not $var1, $var2. Why?
  echo "$var1 is greater than $var2"
fi     # 5 is greater than 4

exit 0
```

[^1]: A _token_ is a symbol or short string with a special meaning attached to it (a [[x17129#^METAMEANINGREF|meta-meaning]]). In Bash, certain tokens, such as **[[special-characters#^DOTREF|** and [. (dot-command)]], may expand to _keywords_ and commands.
