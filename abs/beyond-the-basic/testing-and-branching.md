---
title: 11.4. Testing and Branching
---

The **case** and **select** constructs are technically not loops, since they do not iterate the execution of a code block. Like loops, however, they direct program flow according to conditions at the top or bottom of the block.

**Controlling program flow in a code block**

**case (in) / esac**

The **case** construct is the shell scripting analog to _switch_ in **C/C++**. It permits branching to one of a number of code blocks, depending on condition tests. It serves as a kind of shorthand for multiple if/then/else statements and is an appropriate tool for creating menus.

case "$variable" in

 "$condition1" )
 command...
 ;;

 "$condition2" )
 command...
 ;;
  
  
**esac**

> [!note]
> - Quoting the variables is not mandatory, since word splitting does not take place.
> - Each test line ends with a right paren **)**. [^1]
> - Each condition block ends with a _double_ semicolon ;;.
> - If a condition tests _true_, then the associated commands execute and the **case** block terminates.
> - The entire **case** block ends with an **esac** (_case_ spelled backwards).|

###### Example 11-25. Using *case*

```bash
#!/bin/bash
# Testing ranges of characters.

echo; echo "Hit a key, then hit return."
read Keypress

case "$Keypress" in
  [[:lower:]]   ) echo "Lowercase letter";;
  [[:upper:]]   ) echo "Uppercase letter";;
  [0-9]         ) echo "Digit";;
  *             ) echo "Punctuation, whitespace, or other";;
esac      #  Allows ranges of characters in [square brackets],
          #+ or POSIX ranges in [[double square brackets.

#  In the first version of this example,
#+ the tests for lowercase and uppercase characters were
#+ [a-z] and [A-Z].
#  This no longer works in certain locales and/or Linux distros.
#  POSIX is more portable.
#  Thanks to Frank Wang for pointing this out.

#  Exercise:
#  --------
#  As the script stands, it accepts a single keystroke, then terminates.
#  Change the script so it accepts repeated input,
#+ reports on each keystroke, and terminates only when "X" is hit.
#  Hint: enclose everything in a "while" loop.

exit 0
```

###### Example 11-26. Creating menus using *case*

```bash
#!/bin/bash

# Crude address database

clear # Clear the screen.

echo "          Contact List"
echo "          ------- ----"
echo "Choose one of the following persons:" 
echo
echo "[E]vans, Roland"
echo "[J]ones, Mildred"
echo "[S]mith, Julie"
echo "[Z]ane, Morris"
echo

read person

case "$person" in
# Note variable is quoted.

  "E" | "e" )
  # Accept upper or lowercase input.
  echo
  echo "Roland Evans"
  echo "4321 Flash Dr."
  echo "Hardscrabble, CO 80753"
  echo "(303) 734-9874"
  echo "(303) 734-9892 fax"
  echo "revans@zzy.net"
  echo "Business partner & old friend"
  ;;
# Note double semicolon to terminate each option.

  "J" | "j" )
  echo
  echo "Mildred Jones"
  echo "249 E. 7th St., Apt. 19"
  echo "New York, NY 10009"
  echo "(212) 533-2814"
  echo "(212) 533-9972 fax"
  echo "milliej@loisaida.com"
  echo "Ex-girlfriend"
  echo "Birthday: Feb. 11"
  ;;

# Add info for Smith & Zane later.

          * )
   # Default option.	  
   # Empty input (hitting RETURN) fits here, too.
   echo
   echo "Not yet in database."
  ;;

esac

echo

#  Exercise:
#  --------
#  Change the script so it accepts multiple inputs,
#+ instead of terminating after displaying just one address.

exit 0
```

An exceptionally clever use of **case** involves testing for command-line parameters.

```bash
#! /bin/bash

case "$1" in
  "") echo "Usage: ${0##*/} <filename>"; exit $E_PARAM;;
                      # No command-line parameters,
                      # or first parameter empty.
# Note that ${0##*/} is ${var##pattern} param substitution.
                      # Net result is $0.

  -*) FILENAME=./$1;;   #  If filename passed as argument ($1)
                      #+ starts with a dash,
                      #+ replace it with ./$1
                      #+ so further commands don't interpret it
                      #+ as an option.

  * ) FILENAME=$1;;     # Otherwise, $1.
esac
```

Here is a more straightforward example of command-line parameter handling:

```bash
#! /bin/bash


while [ $# -gt 0 ]; do    # Until you run out of parameters . . .
  case "$1" in
    -d|--debug)
              # "-d" or "--debug" parameter?
              DEBUG=1
              ;;
    -c|--conf)
              CONFFILE="$2"
              shift
              if [ ! -f $CONFFILE ]; then
                echo "Error: Supplied file doesn't exist!"
                exit $E_CONFFILE     # File not found error.
              fi
              ;;
  esac
  shift       # Check next set of parameters.
done

#  From Stefano Falsetto's "Log2Rot" script,
#+ part of his "rottlog" package.
#  Used with permission.
```

###### Example 11-27. Using _command substitution_ to generate the *case* variable

```bash
#!/bin/bash
# case-cmd.sh: Using command substitution to generate a "case" variable.

case $( arch ) in   # $( arch ) returns machine architecture.
                    # Equivalent to 'uname -m' ...
  i386 ) echo "80386-based machine";;
  i486 ) echo "80486-based machine";;
  i586 ) echo "Pentium-based machine";;
  i686 ) echo "Pentium2+-based machine";;
  *    ) echo "Other type of machine";;
esac

exit 0
```

A **case** construct can filter strings for [[globbing.html|globbing]] patterns.

###### Example 11-28. Simple string matching

```bash

#!/bin/bash
# match-string.sh: Simple string matching
#                  using a 'case' construct.

match_string ()
{ # Exact string match.
  MATCH=0
  E_NOMATCH=90
  PARAMS=2     # Function requires 2 arguments.
  E_BAD_PARAMS=91

  [ $# -eq $PARAMS ] || return $E_BAD_PARAMS

  case "$1" in
  "$2") return $MATCH;;
  *   ) return $E_NOMATCH;;
  esac

}  


a=one
b=two
c=three
d=two


match_string $a     # wrong number of parameters
echo $?             # 91

match_string $a $b  # no match
echo $?             # 90

match_string $b $d  # match
echo $?             # 0


exit 0		    
```

###### Example 11-29. Checking for alphabetic input

```bash
#!/bin/bash
# isalpha.sh: Using a "case" structure to filter a string.

SUCCESS=0
FAILURE=1   #  Was FAILURE=-1,
            #+ but Bash no longer allows negative return value.

isalpha ()  # Tests whether *first character* of input string is alphabetic.
{
if [ -z "$1" ]                # No argument passed?
then
  return $FAILURE
fi

case "$1" in
  [a-zA-Z]*) return $SUCCESS;;  # Begins with a letter?
  *        ) return $FAILURE;;
esac
}             # Compare this with "isalpha ()" function in C.


isalpha2 ()   # Tests whether *entire string* is alphabetic.
{
  [ $# -eq 1 ] || return $FAILURE

  case $1 in
  *[!a-zA-Z]*|"") return $FAILURE;;
               *) return $SUCCESS;;
  esac
}

isdigit ()    # Tests whether *entire string* is numerical.
{             # In other words, tests for integer variable.
  [ $# -eq 1 ] || return $FAILURE

  case $1 in
    *[!0-9]*|"") return $FAILURE;;
              *) return $SUCCESS;;
  esac
}



check_var ()  # Front-end to isalpha ().
{
if isalpha "$@"
then
  echo "\"$*\" begins with an alpha character."
  if isalpha2 "$@"
  then        # No point in testing if first char is non-alpha.
    echo "\"$*\" contains only alpha characters."
  else
    echo "\"$*\" contains at least one non-alpha character."
  fi  
else
  echo "\"$*\" begins with a non-alpha character."
              # Also "non-alpha" if no argument passed.
fi

echo

}

digit_check ()  # Front-end to isdigit ().
{
if isdigit "$@"
then
  echo "\"$*\" contains only digits [0 - 9]."
else
  echo "\"$*\" has at least one non-digit character."
fi

echo

}

a=23skidoo
b=H3llo
c=-What?
d=What?
e=$(echo $b)   # Command substitution.
f=AbcDef
g=27234
h=27a34
i=27.34

check_var $a
check_var $b
check_var $c
check_var $d
check_var $e
check_var $f
check_var     # No argument passed, so what happens?
#
digit_check $g
digit_check $h
digit_check $i


exit 0        # Script improved by S.C.

# Exercise:
# --------
#  Write an 'isfloat ()' function that tests for floating point numbers.
#  Hint: The function duplicates 'isdigit ()',
#+ but adds a test for a mandatory decimal point.
```

**select**

The **select** construct, adopted from the Korn Shell, is yet another tool for building menus.

select variable [in list]
do
 command...
 break
done

This prompts the user to enter one of the choices presented in the variable list. Note that **select** uses the $PS3 prompt (#? ) by default, but this may be changed.

###### Example 11-30. Creating menus using *select*

```bash
#!/bin/bash

PS3='Choose your favorite vegetable: ' # Sets the prompt string.
                                       # Otherwise it defaults to #? .

echo

select vegetable in "beans" "carrots" "potatoes" "onions" "rutabagas"
do
  echo
  echo "Your favorite veggie is $vegetable."
  echo "Yuck!"
  echo
  break  # What happens if there is no 'break' here?
done

exit

# Exercise:
# --------
#  Fix this script to accept user input not specified in
#+ the "select" statement.
#  For example, if the user inputs "peas,"
#+ the script would respond "Sorry. That is not on the menu."
```

If **in _list_** is omitted, then **select** uses the list of command line arguments ($@) passed to the script or the function containing the **select** construct.

Compare this to the behavior of a

**for** _variable_ [in _list_]

construct with the **in _list_** omitted.

###### Example 11-31. Creating menus using *select* in a function

```bash
#!/bin/bash

PS3='Choose your favorite vegetable: '

echo

choice_of()
{
select vegetable
# [in list] omitted, so 'select' uses arguments passed to function.
do
  echo
  echo "Your favorite veggie is $vegetable."
  echo "Yuck!"
  echo
  break
done
}

choice_of beans rice carrots radishes rutabaga spinach
#         $1    $2   $3      $4       $5       $6
#         passed to choice_of() function

exit 0
```

See also [[bash-version-2#^RESISTOR|Example 37-3]].

[^1]: Pattern-match lines may also _start_ with a **(** left paren to give the layout a more structured appearance.

    ```bash
    case $( arch ) in   # $( arch ) returns machine architecture.
      ( i386 ) echo "80386-based machine";;
    # ^      ^
      ( i486 ) echo "80486-based machine";;
      ( i586 ) echo "Pentium-based machine";;
      ( i686 ) echo "Pentium2+-based machine";;
      (    * ) echo "Other type of machine";;
    esac
    ```
