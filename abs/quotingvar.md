# 5.1. Quoting Variables

When referencing a variable, it is generally advisable to enclose its name in double quotes. This prevents reinterpretation of all special characters within the quoted string -- except $, ` (backquote), and \ (escape). [[varsubn#^EX9|^1] Keeping $ as a special character within double quotes permits referencing a quoted variable (_"$variable"_), that is, replacing the variable with its value (see [Example 4-1]], above).

Use double quotes to prevent word splitting. [[special-chars#^WHITESPACEREF|^2] An argument enclosed in double quotes presents itself as a single word, even if it contains [whitespace]] separators.

|   |
|---|
|List="one two three"

for a in $List     # Splits the variable in parts at whitespace.
do
  echo "$a"
done
# one
# two
# three

echo "---"

for a in "$List"   # Preserves whitespace in a single variable.
do #     ^     ^
  echo "$a"
done
# one two three|

A more elaborate example:

|   |
|---|
|variable1="a variable containing five words"
COMMAND This is $variable1    # Executes COMMAND with 7 arguments:
# "This" "is" "a" "variable" "containing" "five" "words"

COMMAND "This is $variable1"  # Executes COMMAND with 1 argument:
# "This is a variable containing five words"


variable2=""    # Empty.

COMMAND $variable2 $variable2 $variable2
                # Executes COMMAND with no arguments. 
COMMAND "$variable2" "$variable2" "$variable2"
                # Executes COMMAND with 3 empty arguments. 
COMMAND "$variable2 $variable2 $variable2"
                # Executes COMMAND with 1 argument (2 spaces). 

# Thanks, St�phane Chazelas.|

|   |   |
|---|---|
|![[../images/tip.gif|Tip]]|Enclosing the arguments to an **echo** statement in double quotes is necessary only when word splitting or preservation of [[special-chars#^WHITESPACEREF|whitespace]] is an issue.|

**Example 5-1. Echoing Weird Variables**

|   |
|---|
|#!/bin/bash
# weirdvars.sh: Echoing weird variables.

echo

var="'(]\\{}\$\""
echo $var        # '(]\{}$"
echo "$var"      # '(]\{}$"     Doesn't make a difference.

echo

IFS='\'
echo $var        # '(] {}$"     \ converted to space. Why?
echo "$var"      # '(]\{}$"

# Examples above supplied by Stephane Chazelas.

echo

var2="\\\\\""
echo $var2       #   "
echo "$var2"     # \\"
echo
# But ... var2="\\\\"" is illegal. Why?
var3='\\\\'
echo "$var3"     # \\\\
# Strong quoting works, though.


# ************************************************************ #
# As the first example above shows, nesting quotes is permitted.

echo "$(echo '"')"           # "
#    ^           ^


# At times this comes in useful.

var1="Two bits"
echo "\$var1 = "$var1""      # $var1 = Two bits
#    ^                ^

# Or, as Chris Hiestand points out ...

if [[ "$(du "$My_File1")" -gt "$(du "$My_File2")" ]]
#     ^     ^         ^ ^     ^     ^         ^ ^
then
  ...
fi
# ************************************************************ #|

Single quotes (' ') operate similarly to double quotes, but do not permit referencing variables, since the special meaning of $ is turned off. Within single quotes, _every_ special character except ' gets interpreted literally. Consider single quotes ("full quoting") to be a stricter method of quoting than double quotes ("partial quoting").

|   |   |
|---|---|
|![[../images/note.gif|Note]]|Since even the escape character (\) gets a literal interpretation within single quotes, trying to enclose a single quote within single quotes will not yield the expected result.

\|   \|
\|---\|
\|echo "Why can't I write 's between single quotes"

echo

# The roundabout method.
echo 'Why can'\''t I write '"'"'s between single quotes'
#    \\|-------\\|  \\|----------\\|   \\|-----------------------\\|
# Three single-quoted strings, with escaped and quoted single quotes between.

# This example courtesy of St�phane Chazelas.\||

|[[quotingvar#^AEN2630|[1]]]|Encapsulating "!" within double quotes gives an error when used _from the command line_. This is interpreted as a [[histcommands.html|history command]]. Within a script, though, this problem does not occur, since the Bash history mechanism is disabled then.

Of more concern is the _apparently_ inconsistent behavior of _\_ within double quotes, and especially following an **echo -e** command.

\|   \|
\|---\|
\|bash$ **echo hello\!**
hello!
bash$ **echo "hello\!"**
hello\!

bash$ **echo \**
>
bash$ **echo "\"**
>
bash$ **echo \a**
a
bash$ **echo "\a"**
\a

bash$ **echo x\ty**
xty
bash$ **echo "x\ty"**
x\ty

bash$ **echo -e x\ty**
xty
bash$ **echo -e "x\ty"**
x       y\|

Double quotes following an _echo_ _sometimes_ escape _\_. Moreover, the -e option to _echo_ causes the "\t" to be interpreted as a _tab_.

(Thank you, Wayne Pollock, for pointing this out, and Geoff Lee and Daniel Barclay for explaining it.)|
[^2]: "Word splitting," in this context, means dividing a character string into separate and discrete arguments.

