---
title: 4.2. Variable Assignment
---
## =

the assignment operator (_no space before and after_)

> [!caution]
> Do not confuse this with [[other-comparison-operators#^EQUALSIGNREF|=]] and [[other-comparison-operators#^EQUALREF|-eq]], which [[tests#^IFTHEN|test]], rather than assign!
>
> Note that = can be either an _assignment_ or a _test_ operator, depending on context.

###### Example 4-2. Plain Variable Assignment

```bash
#!/bin/bash
# Naked variables

echo

# When is a variable "naked", i.e., lacking the '$' in front?
# When it is being assigned, rather than referenced.

# Assignment
a=879
echo "The value of \"a\" is $a."

# Assignment using 'let'
let a=16+5
echo "The value of \"a\" is now $a."

echo

# In a 'for' loop (really, a type of disguised assignment):
echo -n "Values of \"a\" in the loop are: "
for a in 7 8 9 11
do
  echo -n "$a "
done

echo
echo

# In a 'read' statement (also a type of assignment):
echo -n "Enter \"a\" "
read a
echo "The value of \"a\" is now $a."

echo

exit 0
```

###### Example 4-3. Variable Assignment, plain and fancy

```bash
#!/bin/bash

a=23              # Simple case
echo $a
b=$a
echo $b

# Now, getting a little bit fancier (command substitution).

a=`echo Hello!`   # Assigns result of 'echo' command to 'a' ...
echo $a
#  Note that including an exclamation mark (!) within a
#+ command substitution construct will not work from the command-line,
#+ since this triggers the Bash "history mechanism."
#  Inside a script, however, the history functions are disabled by default.

a=`ls -l`         # Assigns result of 'ls -l' command to 'a'
echo $a           # Unquoted, however, it removes tabs and newlines.
echo
echo "$a"         # The quoted variable preserves whitespace.
                  # (See the chapter on "Quoting.")

exit 0
```

Variable assignment using the _$(...)_ mechanism (a newer method than [[command-substitution#^BACKQUOTESREF|backquotes]]). This is likewise a form of [[command-substitution#^COMMANDSUBREF|command substitution]].

```bash
# From /etc/rc.d/rc.local
R=$(cat /etc/redhat-release)
arch=$(uname -m)
```
