---
title: 16.2. Complex Commands
---

**Commands for more advanced users**

**find**

-exec _COMMAND_ \;

Carries out _COMMAND_ on each file that **find** matches. The command sequence terminates with ; (the ";" is [[escapingsection#^ESCP|escaped]] to make certain the shell passes it to **find** literally, without interpreting it as a special character).

```bash
bash$ find ~/ -name '*.txt'
/home/bozo/.kde/share/apps/karm/karmdata.txt
 /home/bozo/misc/irmeyc.txt
 /home/bozo/test-scripts/1.txt
	      
```

If _COMMAND_ contains {}, then **find** substitutes the full path name of the selected file for "{}".

```bash
find ~/ -name 'core*' -exec rm {} \;
# Removes all core dump files from user's home directory.
```

```bash
find /home/bozo/projects -mtime -1
#                               ^   Note minus sign!
#  Lists all files in /home/bozo/projects directory tree
#+ that were modified within the last day (current_day - 1).
#
find /home/bozo/projects -mtime 1
#  Same as above, but modified *exactly* one day ago.
#
#  mtime = last modification time of the target file
#  ctime = last status change time (via 'chmod' or otherwise)
#  atime = last access time

DIR=/home/bozo/junk_files
find "$DIR" -type f -atime +5 -exec rm {} \;
#                          ^           ^^
#  Curly brackets are placeholder for the path name output by "find."
#
#  Deletes all files in "/home/bozo/junk_files"
#+ that have not been accessed in *at least* 5 days (plus sign ... +5).
#
#  "-type filetype", where
#  f = regular file
#  d = directory
#  l = symbolic link, etc.
#
#  (The 'find' manpage and info page have complete option listings.)
```

```bash
find /etc -exec grep '[0-9][0-9]*[.][0-9][0-9]*[.][0-9][0-9]*[.][0-9][0-9]*' {} \;

# Finds all IP addresses (xxx.xxx.xxx.xxx) in /etc directory files.
# There a few extraneous hits. Can they be filtered out?

# Possibly by:

find /etc -type f -exec cat '{}' \; | tr -c '.[:digit:]' '\n' \
| grep '^[^.][^.]*\.[^.][^.]*\.[^.][^.]*\.[^.][^.]*$'
#
#  [:digit:] is one of the character classes
#+ introduced with the POSIX 1003.2 standard. 

# Thanks, Stéphane Chazelas. 
```

> [!note]
> The -exec option to **find** should not be confused with the [[internal#^EXECREF|exec]] shell builtin.

###### Example 16-3. *Badname*, eliminate file names in current directory containing bad characters and [[special-characters#Whitespace|whitespace]].

```bash
#!/bin/bash
# badname.sh
# Delete filenames in current directory containing bad characters.

for filename in *
do
  badname=`echo "$filename" | sed -n /[\+\{\;\"\\\=\?~\(\)\<\>\&\*\|\$]/p`
# badname=`echo "$filename" | sed -n '/[+{;"\=?~()<>&*|$]/p'`  also works.
# Deletes files containing these nasties:     + { ; " \ = ? ~ ( ) < > & * | $
#
  rm $badname 2>/dev/null
#             ^^^^^^^^^^^ Error messages deep-sixed.
done

# Now, take care of files containing all manner of whitespace.
find . -name "* *" -exec rm -f {} \;
# The path name of the file that _find_ finds replaces the "{}".
# The '\' ensures that the ';' is interpreted literally, as end of command.

exit 0

#---------------------------------------------------------------------
# Commands below this line will not execute because of _exit_ command.

# An alternative to the above script:
find . -name '*[+{;"\\=?~()<>&*|$ ]*' -maxdepth 0 \
-exec rm -f '{}' \;
#  The "-maxdepth 0" option ensures that _find_ will not search
#+ subdirectories below $PWD.

# (Thanks, S.C.)
```

###### Example 16-4. Deleting a file by its *inode* number

```bash
#!/bin/bash
# idelete.sh: Deleting a file by its inode number.

#  This is useful when a filename starts with an illegal character,
#+ such as ? or -.

ARGCOUNT=1                      # Filename arg must be passed to script.
E_WRONGARGS=70
E_FILE_NOT_EXIST=71
E_CHANGED_MIND=72

if [ $# -ne "$ARGCOUNT" ]
then
  echo "Usage: `basename $0` filename"
  exit $E_WRONGARGS
fi  

if [ ! -e "$1" ]
then
  echo "File \""$1"\" does not exist."
  exit $E_FILE_NOT_EXIST
fi  

inum=`ls -i | grep "$1" | awk '{print $1}'`
# inum = inode (index node) number of file
# -----------------------------------------------------------------------
# Every file has an inode, a record that holds its physical address info.
# -----------------------------------------------------------------------

echo; echo -n "Are you absolutely sure you want to delete \"$1\" (y/n)? "
# The '-v' option to 'rm' also asks this.
read answer
case "$answer" in
[nN]) echo "Changed your mind, huh?"
      exit $E_CHANGED_MIND
      ;;
*)    echo "Deleting file \"$1\".";;
esac

find . -inum $inum -exec rm {} \;
#                           ^^
#        Curly brackets are placeholder
#+       for text output by "find."
echo "File "\"$1"\" deleted!"

exit 0
```

The **find** command also works without the -exec option.

```bash
#!/bin/bash
#  Find suid root files.
#  A strange suid file might indicate a security hole,
#+ or even a system intrusion.

directory="/usr/sbin"
# Might also try /sbin, /bin, /usr/bin, /usr/local/bin, etc.
permissions="+4000"  # suid root (dangerous!)


for file in $( find "$directory" -perm "$permissions" )
do
  ls -ltF --author "$file"
done
```

See [[file-and-archiving-commands#^EX48|Example 16-30]], [[special-chars#^EX58|Example 3-4]], and [[loops1#^FINDSTRING|Example 11-10]] for scripts using **find**. Its [[basic#^MANREF|manpage]] provides more detail on this complex and powerful command.

**xargs**

A filter for feeding arguments to a command, and also a tool for assembling the commands themselves. It breaks a data stream into small enough chunks for filters and commands to process. Consider it as a powerful replacement for [[commandsub#^BACKQUOTESREF|backquotes]]. In situations where [[commandsub#^COMMANDSUBREF|command substitution]] fails with a too many arguments error, substituting **xargs** often works. [^1] Normally, **xargs** reads from stdin or from a pipe, but it can also be given the output of a file.

The default command for **xargs** is [[internal#^ECHOREF|echo]]. This means that input piped to **xargs** may have linefeeds and other whitespace characters stripped out.

```bash
bash$ ls -l
total 0
 -rw-rw-r--    1 bozo  bozo         0 Jan 29 23:58 file1
 -rw-rw-r--    1 bozo  bozo         0 Jan 29 23:58 file2



bash$ ls -l | xargs
total 0 -rw-rw-r-- 1 bozo bozo 0 Jan 29 23:58 file1 -rw-rw-r-- 1 bozo bozo 0 Jan...



bash$ find ~/mail -type f | xargs grep "Linux"
./misc:User-Agent: slrn/0.9.8.1 (Linux)
 ./sent-mail-jul-2005: hosted by the Linux Documentation Project.
 ./sent-mail-jul-2005: (Linux Documentation Project Site, rtf version)
 ./sent-mail-jul-2005: Subject: Criticism of Bozo's Windows/Linux article
 ./sent-mail-jul-2005: while mentioning that the Linux ext2/ext3 filesystem
 . . .
	      
```

**ls | xargs -p -l gzip** [[file-and-archiving-commands#^GZIPREF|gzips]] every file in current directory, one at a time, prompting before each operation.

> [!note]
> Note that _xargs_ processes the arguments passed to it sequentially, _one at a time_.
>
> ```bash
> bash$ find /usr/bin | xargs file
> /usr/bin:          directory
>  /usr/bin/foomatic-ppd-options:          perl script text executable
>  . . .
> 	      
> ```

> [!tip] An interesting _xargs_ option is -n _NN_, which limits to _NN_ the number of arguments passed.
>
> **ls \| xargs -n 8 echo** lists the files in the current directory in 8 columns.

> [!tip]
> Another useful option is -0, in combination with **find -print0** or **grep -lZ**. This allows handling arguments containing whitespace or quotes.
>
> **find / -type f -print0 \| xargs -0 grep -liwZ GUI \| xargs -0 rm -f**
>
> **grep -rliwZ GUI / \| xargs -0 rm -f**
>
> Either of the above will remove any file containing "GUI". _(Thanks, S.C.)_
>
> Or:
>
> ```bash
> cat /proc/"$pid"/"$OPTION" | xargs -0 echo
> #  Formats output:         ^^^^^^^^^^^^^^^
> #  From Han Holl's fixup of "get-commandline.sh"
> #+ script in "/dev and /proc" chapter.
> ```

> [!tip]
> The -P option to _xargs_ permits running processes in parallel. This speeds up execution in a machine with a multicore CPU.
>
> ```bash
> #!/bin/bash
> 
> ls *gif | xargs -t -n1 -P2 gif2png
> # Converts all the gif images in current directory to png.
> 
> # Options:
> # =======
> # -t    Print command to stderr.
> # -n1   At most 1 argument per command line.
> # -P2   Run up to 2 processes simultaneously.
> 
> # Thank you, Roberto Polli, for the inspiration.
> ```

###### Example 16-5. Logfile: Using *xargs* to monitor system log

```bash
#!/bin/bash

# Generates a log file in current directory
# from the tail end of /var/log/messages.

# Note: /var/log/messages must be world readable
# if this script invoked by an ordinary user.
#         #root chmod 644 /var/log/messages

LINES=5

( date; uname -a ) >>logfile
# Time and machine name
echo ---------------------------------------------------------- >>logfile
tail -n $LINES /var/log/messages | xargs | fmt -s >>logfile
echo >>logfile
echo >>logfile

exit 0

#  Note:
#  ----
#  As Frank Wang points out,
#+ unmatched quotes (either single or double quotes) in the source file
#+ may give xargs indigestion.
#
#  He suggests the following substitution for line 15:
#  tail -n $LINES /var/log/messages | tr -d "\"'" | xargs | fmt -s >>logfile



#  Exercise:
#  --------
#  Modify this script to track changes in /var/log/messages at intervals
#+ of 20 minutes.
#  Hint: Use the "watch" command. 
```

[[moreadv#^CURLYBRACKETSREF|As in **find**]], a curly bracket pair serves as a placeholder for replacement text.

###### Example 16-6. Copying files in current directory to another

```bash
#!/bin/bash
# copydir.sh

#  Copy (verbose) all files in current directory ($PWD)
#+ to directory specified on command-line.

E_NOARGS=85

if [ -z "$1" ]   # Exit if no argument given.
then
  echo "Usage: `basename $0` directory-to-copy-to"
  exit $E_NOARGS
fi  

ls . | xargs -i -t cp ./{} $1
#            ^^ ^^      ^^
#  -t is "verbose" (output command-line to stderr) option.
#  -i is "replace strings" option.
#  {} is a placeholder for output text.
#  This is similar to the use of a curly-bracket pair in "find."
#
#  List the files in current directory (ls .),
#+ pass the output of "ls" as arguments to "xargs" (-i -t options),
#+ then copy (cp) these arguments ({}) to new directory ($1).  
#
#  The net result is the exact equivalent of
#+   cp * $1
#+ unless any of the filenames has embedded "whitespace" characters.

exit 0
```

###### Example 16-7. Killing processes by name

```bash
#!/bin/bash
# kill-byname.sh: Killing processes by name.
# Compare this script with kill-process.sh.

#  For instance,
#+ try "./kill-byname.sh xterm" --
#+ and watch all the xterms on your desktop disappear.

#  Warning:
#  -------
#  This is a fairly dangerous script.
#  Running it carelessly (especially as root)
#+ can cause data loss and other undesirable effects.

E_BADARGS=66

if test -z "$1"  # No command-line arg supplied?
then
  echo "Usage: `basename $0` Process(es)_to_kill"
  exit $E_BADARGS
fi


PROCESS_NAME="$1"
ps ax | grep "$PROCESS_NAME" | awk '{print $1}' | xargs -i kill {} 2&>/dev/null
#                                                       ^^      ^^

# ---------------------------------------------------------------
# Notes:
# -i is the "replace strings" option to xargs.
# The curly brackets are the placeholder for the replacement.
# 2&>/dev/null suppresses unwanted error messages.
#
# Can  grep "$PROCESS_NAME" be replaced by pidof "$PROCESS_NAME"?
# ---------------------------------------------------------------

exit $?

#  The "killall" command has the same effect as this script,
#+ but using it is not quite as educational.
```

###### Example 16-8. Word frequency analysis using *xargs*

```bash
#!/bin/bash
# wf2.sh: Crude word frequency analysis on a text file.

# Uses 'xargs' to decompose lines of text into single words.
# Compare this example to the "wf.sh" script later on.


# Check for input file on command-line.
ARGS=1
E_BADARGS=85
E_NOFILE=86

if [ $# -ne "$ARGS" ]
# Correct number of arguments passed to script?
then
  echo "Usage: `basename $0` filename"
  exit $E_BADARGS
fi

if [ ! -f "$1" ]       # Does file exist?
then
  echo "File \"$1\" does not exist."
  exit $E_NOFILE
fi



#####################################################
cat "$1" | xargs -n1 | \
#  List the file, one word per line. 
tr A-Z a-z | \
#  Shift characters to lowercase.
sed -e 's/\.//g'  -e 's/\,//g' -e 's/ /\
/g' | \
#  Filter out periods and commas, and
#+ change space between words to linefeed,
sort | uniq -c | sort -nr
#  Finally remove duplicates, prefix occurrence count
#+ and sort numerically.
#####################################################

#  This does the same job as the "wf.sh" example,
#+ but a bit more ponderously, and it runs more slowly (why?).

exit $?
```

**expr**

All-purpose expression evaluator: Concatenates and evaluates the arguments according to the operation given (arguments must be separated by spaces). Operations may be arithmetic, comparison, string, or logical.

**expr 3 + 5**

returns 8

**expr 5 % 3**

returns 2

**expr 1 / 0**

returns the error message, expr: division by zero

Illegal arithmetic operations not allowed.

**expr 5 \* 3**

returns 15

The multiplication operator must be escaped when used in an arithmetic expression with **expr**.

**y=`expr $y + 1`**

Increment a variable, with the same effect as **let y=y+1** and **y=$(($y+1))**. This is an example of [[arithmetic-expansion#^ARITHEXPREF|arithmetic expansion]].

**z=`expr substr $string $position $length`**

Extract substring of $length characters, starting at $position.

###### Example 16-9. Using *expr*

```bash
#!/bin/bash

# Demonstrating some of the uses of 'expr'
# =======================================

echo

# Arithmetic Operators
# ---------- ---------

echo "Arithmetic Operators"
echo
a=`expr 5 + 3`
echo "5 + 3 = $a"

a=`expr $a + 1`
echo
echo "a + 1 = $a"
echo "(incrementing a variable)"

a=`expr 5 % 3`
# modulo
echo
echo "5 mod 3 = $a"

echo
echo

# Logical Operators
# ------- ---------

#  Returns 1 if true, 0 if false,
#+ opposite of normal Bash convention.

echo "Logical Operators"
echo

x=24
y=25
b=`expr $x = $y`         # Test equality.
echo "b = $b"            # 0  ( $x -ne $y )
echo

a=3
b=`expr $a \> 10`
echo 'b=`expr $a \> 10`, therefore...'
echo "If a > 10, b = 0 (false)"
echo "b = $b"            # 0  ( 3 ! -gt 10 )
echo

b=`expr $a \< 10`
echo "If a < 10, b = 1 (true)"
echo "b = $b"            # 1  ( 3 -lt 10 )
echo
# Note escaping of operators.

b=`expr $a \<= 3`
echo "If a <= 3, b = 1 (true)"
echo "b = $b"            # 1  ( 3 -le 3 )
# There is also a "\>=" operator (greater than or equal to).


echo
echo



# String Operators
# ------ ---------

echo "String Operators"
echo

a=1234zipper43231
echo "The string being operated upon is \"$a\"."

# length: length of string
b=`expr length $a`
echo "Length of \"$a\" is $b."

# index: position of first character in substring
#        that matches a character in string
b=`expr index $a 23`
echo "Numerical position of first \"2\" in \"$a\" is \"$b\"."

# substr: extract substring, starting position & length specified
b=`expr substr $a 2 6`
echo "Substring of \"$a\", starting at position 2,\
and 6 chars long is \"$b\"."


#  The default behavior of the 'match' operations is to
#+ search for the specified match at the BEGINNING of the string.
#
#       Using Regular Expressions ...
b=`expr match "$a" '[0-9]*'`               #  Numerical count.
echo Number of digits at the beginning of \"$a\" is $b.
b=`expr match "$a" '\([0-9]*\)'`           #  Note that escaped parentheses
#                   ==      ==             #+ trigger substring match.
echo "The digits at the beginning of \"$a\" are \"$b\"."

echo

exit 0
```

> [!important]
> The [[special-chars#^NULLREF|: (_null_)]] operator can substitute for **match**. For example, **b=`expr $a : [0-9]*`** is the exact equivalent of **b=`expr match $a [0-9]*`** in the above listing.
>
> ```bash
> #!/bin/bash
> 
> echo
> echo "String operations using \"expr \$string : \" construct"
> echo "==================================================="
> echo
> 
> a=1234zipper5FLIPPER43231
> 
> echo "The string being operated upon is \"`expr "$a" : '\(.*\)'`\"."
> #     Escaped parentheses grouping operator.            ==  ==
> 
> #       ***************************
> #+          Escaped parentheses
> #+           match a substring
> #       ***************************
> 
> 
> #  If no escaped parentheses ...
> #+ then 'expr' converts the string operand to an integer.
> 
> echo "Length of \"$a\" is `expr "$a" : '.*'`."   # Length of string
> 
> echo "Number of digits at the beginning of \"$a\" is `expr "$a" : '[0-9]*'`."
> 
> # ------------------------------------------------------------------------- #
> 
> echo
> 
> echo "The digits at the beginning of \"$a\" are `expr "$a" : '\([0-9]*\)'`."
> #                                                             ==      ==
> echo "The first 7 characters of \"$a\" are `expr "$a" : '\(.......\)'`."
> #         =====                                          ==       ==
> # Again, escaped parentheses force a substring match.
> #
> echo "The last 7 characters of \"$a\" are `expr "$a" : '.*\(.......\)'`."
> #         ====                  end of string operator  ^^
> #  (In fact, means skip over one or more of any characters until specified
> #+  substring found.)
> 
> echo
> 
> exit 0
> ```

The above script illustrates how **expr** uses the _escaped parentheses -- \( ... \) --_ grouping operator in tandem with [[regexp#^REGEXREF|regular expression]] parsing to match a substring. Here is a another example, this time from "real life."

```bash
# Strip the whitespace from the beginning and end.
LRFDATE=`expr "$LRFDATE" : '[[:space:]]*\(.*\)[[:space:]]*$'`

#  From Peter Knowles' "booklistgen.sh" script
#+ for converting files to Sony Librie/PRS-50X format.
#  (http://booklistgensh.peterknowles.com)
```

[[wrapper#^PERLREF|Perl]], [[sedawk#^SEDREF|sed]], and [[awk#^AWKREF|awk]] have far superior string parsing facilities. A short **sed** or **awk** "subroutine" within a script (see [[wrapper|Section 36.2]]) is an attractive alternative to **expr**.

See [[string-manipulation|Section 10.1]] for more on using **expr** in string operations.

[^1]: And even when _xargs_ is not strictly necessary, it can speed up execution of a command involving [[time-date-commands#^BATCHPROCREF|batch-processing]] of multiple files.
