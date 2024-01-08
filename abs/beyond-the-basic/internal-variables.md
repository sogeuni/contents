---
title: 9.1. Internal Variables
---


_[[internal-commands-and-builtins#^BUILTINREF|Builtin]] variables:_

variables affecting bash script behavior

$BASH

The path to the _Bash_ binary itself

```bash
bash$ **echo $BASH**
/bin/bash
```

$BASH_ENV

An [[othertypesv#^ENVREF|environmental variable]] pointing to a Bash startup file to be read when a script is invoked

$BASH_SUBSHELL

A variable indicating the [[subshells#^SUBSHELLSREF|subshell]] level. This is a new addition to Bash, [[bashver3#^BASH3REF|version 3]].

See [[subshells#^SUBSHELL|Example 21-1]] for usage.

$BASHPID

_Process ID_ of the current instance of Bash. This is not the same as the [[internal-variables#^PROCCID|$$]] variable, but it often gives the same result.

```bash
bash4$ echo $$
11015


bash4$ echo $BASHPID
11015


bash4$ ps ax | grep bash4
11015 pts/2    R      0:00 bash4
	      
```

But ...

```bash
#!/bin/bash4

echo "\$\$ outside of subshell = $$"                              # 9602
echo "\$BASH_SUBSHELL  outside of subshell = $BASH_SUBSHELL"      # 0
echo "\$BASHPID outside of subshell = $BASHPID"                   # 9602

echo

( echo "\$\$ inside of subshell = $$"                             # 9602
  echo "\$BASH_SUBSHELL inside of subshell = $BASH_SUBSHELL"      # 1
  echo "\$BASHPID inside of subshell = $BASHPID" )                # 9603
  # Note that $$ returns PID of parent process.
```

$BASH_VERSINFO\[n]

A 6-element [[arrays#^ARRAYREF|array]] containing version information about the installed release of Bash. This is similar to $BASH_VERSION, below, but a bit more detailed.

```bash
# Bash version info:

for n in 0 1 2 3 4 5
do
  echo "BASH_VERSINFO[$n] = ${BASH_VERSINFO[$n]}"
done  

# BASH_VERSINFO[0] = 3                      # Major version no.
# BASH_VERSINFO[1] = 00                     # Minor version no.
# BASH_VERSINFO[2] = 14                     # Patch level.
# BASH_VERSINFO[3] = 1                      # Build version.
# BASH_VERSINFO[4] = release                # Release status.
# BASH_VERSINFO[5] = i386-redhat-linux-gnu  # Architecture
                                            # (same as $MACHTYPE).
```

$BASH_VERSION

The version of Bash installed on the system

```bash
bash$ echo $BASH_VERSION
3.2.25(1)-release
	      
```

```bash
tcsh% echo $BASH_VERSION
BASH_VERSION: Undefined variable.
	      
```

Checking `$BASH_VERSION` is a good method of determining which shell is running. [[internal-variables#^SHELLVARREF|$SHELL]] does not necessarily give the correct answer.

$CDPATH

A colon-separated list of search paths available to the [[internal-commands-and-builtins#^CDREF|cd]] command, similar in function to the [[internal-variables#^PATHREF|$PATH]] variable for binaries. The $CDPATH variable may be set in the local [[sample-bashrc#^BASHRC|~/.bashrc]] file.

```bash
bash$ cd bash-doc
bash: cd: bash-doc: No such file or directory


bash$ CDPATH=/usr/share/doc
bash$ cd bash-doc
/usr/share/doc/bash-doc


bash$ echo $PWD
/usr/share/doc/bash-doc
	      
```

$DIRSTACK

The top value in the directory stack [^1] (affected by [[internal-commands-and-builtins#^PUSHDREF|pushd]] and [[internal-commands-and-builtins#^POPDREF|popd]])

This builtin variable corresponds to the [[internal-commands-and-builtins#^DIRSD|dirs]] command, however **dirs** shows the entire contents of the directory stack.

$EDITOR

The default editor invoked by a script, usually **vi** or **emacs**.

$EUID

"effective" user ID number

Identification number of whatever identity the current user has assumed, perhaps by means of [[system#^SUREF|su]].

> [!caution] The `$EUID` is not necessarily the same as the [[internal-variables#^UIDREF|$UID]].

$FUNCNAME

Name of the current function

```bash
xyz23 ()
{
  echo "$FUNCNAME now executing."  # xyz23 now executing.
}

xyz23

echo "FUNCNAME = $FUNCNAME"        # FUNCNAME =
                                   # Null value outside a function.
```

See also [[contributed-scripts#^USEGETOPT|Example A-50]].

$GLOBIGNORE

A list of filename patterns to be excluded from matching in [[globbingref.html|globbing]].

$GROUPS

Groups current user belongs to

This is a listing (array) of the group id numbers for current user, as recorded in [[files#^DATAFILESREF1|/etc/passwd]] and /etc/group.

```bash
root# echo $GROUPS
0


root# echo ${GROUPS[1]}
1


root# echo ${GROUPS[5]}
6
	      
```

$HOME

Home directory of the user, usually /home/username (see [[parameter-substitution#^EX6|Example 10-7]])

$HOSTNAME

The [[system#^HNAMEREF|hostname]] command assigns the system host name at bootup in an init script. However, the gethostname() function sets the Bash internal variable $HOSTNAME. See also [[parameter-substitution#^EX6|Example 10-7]].

$HOSTTYPE

host type

Like [[internal-variables#^MACHTYPEREF|$MACHTYPE]], identifies the system hardware.

```bash
bash$ echo $HOSTTYPE
i686
```

$IFS

internal field separator

This variable determines how Bash recognizes [[special-characters#^FIELDREF|fields]], or word boundaries, when it interprets character strings.

`$IFS` defaults to [[special-characters#^WHITESPACEREF|whitespace]] (space, tab, and newline), but may be changed, for example, to parse a comma-separated data file. Note that [[internal-variables#^APPREF|$*]] uses the first character held in $IFS. See [[quoting-variables#^WEIRDVARS|Example 5-1]].

```bash
bash$ echo "$IFS"

(With $IFS set to default, a blank line displays.)
	      


bash$ echo "$IFS" | cat -vte
 ^I$
 $
(Show whitespace: here a single space, ^I [horizontal tab],
  and newline, and display "$" at end-of-line.)



bash$ bash -c 'set w x y z; IFS=":-;"; echo "$*"'
w:x:y:z
(Read commands from string and assign any arguments to pos params.)
	      
```

Set $IFS to eliminate whitespace in [[special-characters#^PATHNAMEREF|pathnames]].

```bash
IFS="$(printf '\n\t')"   # Per David Wheeler.
```

> [!caution] $IFS does not handle whitespace the same as it does other characters.
>
> **Example 9-1. $IFS and whitespace**
>
> ```bash
> #!/bin/bash
> # ifs.sh
> 
> 
> var1="a+b+c"
> var2="d-e-f"
> var3="g,h,i"
> 
> IFS=+
> # The plus sign will be interpreted as a separator.
> echo $var1     # a b c
> echo $var2     # d-e-f
> echo $var3     # g,h,i
> 
> echo
> 
> IFS="-"
> # The plus sign reverts to default interpretation.
> # The minus sign will be interpreted as a separator.
> echo $var1     # a+b+c
> echo $var2     # d e f
> echo $var3     # g,h,i
> 
> echo
> 
> IFS=","
> # The comma will be interpreted as a separator.
> # The minus sign reverts to default interpretation.
> echo $var1     # a+b+c
> echo $var2     # d-e-f
> echo $var3     # g h i
> 
> echo
> 
> IFS=" "
> # The space character will be interpreted as a separator.
> # The comma reverts to default interpretation.
> echo $var1     # a+b+c
> echo $var2     # d-e-f
> echo $var3     # g,h,i
> 
> # ======================================================== #
> 
> # However ...
> # $IFS treats whitespace differently than other characters.
> 
> output_args_one_per_line()
> {
>   for arg
>   do
>     echo "[$arg]"
>   done #  ^    ^   Embed within brackets, for your viewing pleasure.
> }
> 
> echo; echo "IFS=\" \""
> echo "-------"
> 
> IFS=" "
> var=" a  b c   "
> #    ^ ^^   ^^^
> output_args_one_per_line $var  # output_args_one_per_line `echo " a  b c   "`
> # [a]
> # [b]
> # [c]
> 
> 
> echo; echo "IFS=:"
> echo "-----"
> 
> IFS=:
> var=":a::b:c:::"               # Same pattern as above,
> #    ^ ^^   ^^^                #+ but substituting ":" for " "  ...
> output_args_one_per_line $var
> # []
> # [a]
> # []
> # [b]
> # [c]
> # []
> # []
> 
> # Note "empty" brackets.
> # The same thing happens with the "FS" field separator in awk.
> 
> 
> echo
> 
> exit
> ```
>
> (Many thanks, Stéphane Chazelas, for clarification and above examples.)
>
> See also [[communications#^ISSPAMMER|Example 16-41]], [[loops#^BINGREP|Example 11-8]], and [[x17837#^MAILBOXGREP|Example 19-14]] for instructive examples of using $IFS.

$IGNOREEOF

Ignore EOF: how many end-of-files (control-D) the shell will ignore before logging out.

$LC_COLLATE

Often set in the [[sample-bashrc|.bashrc]] or /etc/profile files, this variable controls collation order in filename expansion and pattern matching. If mishandled, LC_COLLATE can cause unexpected results in [[globbingref|filename globbing]].

> [!note]
> As of version 2.05 of Bash, filename globbing no longer distinguishes between lowercase and uppercase letters in a character range between brackets. For example, **ls [A-M]*** would match both File1.txt and file1.txt. To revert to the customary behavior of bracket matching, set LC_COLLATE to C by an **export LC_COLLATE=C** in /etc/profile and/or ~/.bashrc.

$LC_CTYPE

This internal variable controls character interpretation in [[globbingref.html|globbing]] and pattern matching.

$LINENO

This variable is the line number of the shell script in which this variable appears. It has significance only within the script in which it appears, and is chiefly useful for debugging purposes.

```bash
# *** BEGIN DEBUG BLOCK ***
last_cmd_arg=$_  # Save it.

echo "At line number $LINENO, variable \"v1\" = $v1"
echo "Last command argument processed = $last_cmd_arg"
# *** END DEBUG BLOCK ***
```

$MACHTYPE

machine type

Identifies the system hardware.

```bash
bash$ echo $MACHTYPE
i686
```

$OLDPWD

Old working directory ("OLD-Print-Working-Directory", previous directory you were in).

$OSTYPE

operating system type

```bash
bash$ echo $OSTYPE
linux
```

$PATH

Path to binaries, usually /usr/bin/, /usr/X11R6/bin/, /usr/local/bin, etc.

When given a command, the shell automatically does a hash table search on the directories listed in the _path_ for the executable. The path is stored in the [[othertypesv#^ENVREF|environmental variable]], $PATH, a list of directories, separated by colons. Normally, the system stores the $PATH definition in /etc/profile and/or [[sample-bashrc|~/.bashrc]] (see [[files|Appendix H]]).

```bash
bash$ echo $PATH
/bin:/usr/bin:/usr/local/bin:/usr/X11R6/bin:/sbin:/usr/sbin
```

**PATH=${PATH}:/opt/bin** appends the /opt/bin directory to the current path. In a script, it may be expedient to temporarily add a directory to the path in this way. When the script exits, this restores the original $PATH (a child process, such as a script, may not change the environment of the parent process, the shell).

> [!note] The current "working directory", ./, is usually omitted from the $PATH as a security measure.

$PIPESTATUS

[[arrays#^ARRAYREF|Array]] variable holding [[exit-status#^EXITSTATUSREF|exit status]](es) of last executed _foreground_ [[special-characters#^PIPEREF|pipe]].

```bash
bash$ echo $PIPESTATUS
0

bash$ ls -al | bogus_command
bash: bogus_command: command not found
bash$ echo ${PIPESTATUS[1]}
127

bash$ ls -al | bogus_command
bash: bogus_command: command not found
bash$ echo $?
127
	      
```

The members of the $PIPESTATUS array hold the exit status of each respective command executed in a pipe. $PIPESTATUS[0] holds the exit status of the first command in the pipe, $PIPESTATUS[1] the exit status of the second command, and so on.

> [!caution]
> The $PIPESTATUS variable may contain an erroneous 0 value in a login shell (in releases prior to 3.0 of Bash).
>
> ```bash
> tcsh% bash
> 
> bash$ who | grep nobody | sort
> bash$ echo ${PIPESTATUS[*]}
> 0
> 	    
> ```
>
> The above lines contained in a script would produce the expected 0 1 0 output.
>
> Thank you, Wayne Pollock for pointing this out and supplying the above example.|

> [!note]
> The $PIPESTATUS variable gives unexpected results in some contexts.
>
> ```bash
> bash$ echo $BASH_VERSION
> 3.00.14(1)-release
> 
> bash$ $ ls | bogus_command | wc
> bash: bogus_command: command not found
>  0       0       0
> 
> bash$ echo ${PIPESTATUS[@]}
> 141 127 0
> 
> ```
>
> Chet Ramey attributes the above output to the behavior of [[basic-commands#^LSREF|ls]]. If _ls_ writes to a _pipe_ whose output is not read, then _SIGPIPE_ kills it, and its [[exit-status#^EXITSTATUSREF|exit status]] is 141. Otherwise its exit status is 0, as expected. This likewise is the case for [[textproc#^TRREF|tr]].

> [!note]
> $PIPESTATUS is a "volatile" variable. It needs to be captured immediately after the pipe in question, before any other command intervenes.
>
> ```bash
> bash$ $ ls | bogus_command | wc
> bash: bogus_command: command not found
>  0       0       0
> 
> bash$ echo ${PIPESTATUS[@]}
> 0 127 0
> 
> bash$ echo ${PIPESTATUS[@]}
> 0
> 	      
> ```

> [!note] The [[bashver3#^PIPEFAILREF|pipefail option]] may be useful in cases where $PIPESTATUS does not give the desired information.

$PPID

The $PPID of a process is the process ID (pid) of its parent process. [^2]

Compare this with the [[system#^PIDOFREF|pidof]] command.

$PROMPT_COMMAND

A variable holding a command to be executed just before the primary prompt, $PS1 is to be displayed.

$PS1

This is the main prompt, seen at the command-line.

$PS2

The secondary prompt, seen when additional input is expected. It displays as ">".

$PS3

The tertiary prompt, displayed in a [[testing-and-branching#^SELECTREF|select]] loop (see [[testing-and-branching#^EX31|Example 11-30]]).

$PS4

The quartenary prompt, shown at the beginning of each line of output when invoking a script with the -x _[[options#^OPTIONSREF|verbose trace]_ [option]]. It displays as "+".

As a debugging aid, it may be useful to embed diagnostic information in $PS4.

```bash
P4='$(read time junk < /proc/$$/schedstat; echo "@@@ $time @@@ " )'
# Per suggestion by Erik Brandsberg.
set -x
# Various commands follow ...
```

$PWD

Working directory (directory you are in at the time)

This is the analog to the [[internal-commands-and-builtins#^PWD2REF|pwd]] builtin command.

```bash
#!/bin/bash

E_WRONG_DIRECTORY=85

clear # Clear the screen.

TargetDirectory=/home/bozo/projects/GreatAmericanNovel

cd $TargetDirectory
echo "Deleting stale files in $TargetDirectory."

if [ "$PWD" != "$TargetDirectory" ]
then    # Keep from wiping out wrong directory by accident.
  echo "Wrong directory!"
  echo "In $PWD, rather than $TargetDirectory!"
  echo "Bailing out!"
  exit $E_WRONG_DIRECTORY
fi  

rm -rf *
rm .[A-Za-z0-9]*    # Delete dotfiles.
# rm -f .[^.]* ..?*   to remove filenames beginning with multiple dots.
# (shopt -s dotglob; rm -f *)   will also work.
# Thanks, S.C. for pointing this out.

#  A filename (`basename`) may contain all characters in the 0 - 255 range,
#+ except "/".
#  Deleting files beginning with weird characters, such as -
#+ is left as an exercise. (Hint: rm ./-weirdname or rm -- -weirdname)
result=$?   # Result of delete operations. If successful = 0.

echo
ls -al              # Any files left?
echo "Done."
echo "Old files deleted in $TargetDirectory."
echo

# Various other operations here, as necessary.

exit $result
```

$REPLY

The default value when a variable is not supplied to [[internal-commands-and-builtins#^READREF|read]]. Also applicable to [[testing-and-branching#^SELECTREF|select]] menus, but only supplies the item number of the variable chosen, not the value of the variable itself.

```bash
#!/bin/bash
# reply.sh

# REPLY is the default value for a 'read' command.

echo
echo -n "What is your favorite vegetable? "
read

echo "Your favorite vegetable is $REPLY."
#  REPLY holds the value of last "read" if and only if
#+ no variable supplied.

echo
echo -n "What is your favorite fruit? "
read fruit
echo "Your favorite fruit is $fruit."
echo "but..."
echo "Value of \$REPLY is still $REPLY."
#  $REPLY is still set to its previous value because
#+ the variable $fruit absorbed the new "read" value.

echo

exit 0
```

$SECONDS

The number of seconds the script has been running.

```bash
#!/bin/bash

TIME_LIMIT=10
INTERVAL=1

echo
echo "Hit Control-C to exit before $TIME_LIMIT seconds."
echo

while [ "$SECONDS" -le "$TIME_LIMIT" ]
do   #   $SECONDS is an internal shell variable.
  if [ "$SECONDS" -eq 1 ]
  then
    units=second
  else  
    units=seconds
  fi

  echo "This script has been running $SECONDS $units."
  #  On a slow or overburdened machine, the script may skip a count
  #+ every once in a while.
  sleep $INTERVAL
done

echo -e "\a"  # Beep!

exit 0
```

$SHELLOPTS

The list of enabled shell [[options#^OPTIONSREF|options]], a readonly variable.

```bash
bash$ echo $SHELLOPTS
braceexpand:hashall:histexpand:monitor:history:interactive-comments:emacs
	      
```

$SHLVL

Shell level, how deeply Bash is nested. [^3] If, at the command-line, $SHLVL is 1, then in a script it will increment to 2.

> [!note] This variable is [[subshells#^SUBSHNLEVREF|_not_ affected by subshells]]. Use [[internal-variables#^BASHSUBSHELLREF|$BASH_SUBSHELL]] when you need an indication of subshell nesting.

$TMOUT

If the _$TMOUT_ environmental variable is set to a non-zero value time, then the shell prompt will time out after $time seconds. This will cause a logout.

As of version 2.05b of Bash, it is now possible to use _$TMOUT_ in a script in combination with [[internal-commands-and-builtins#^READREF|read]].

```bash
# Works in scripts for Bash, versions 2.05b and later.

TMOUT=3    # Prompt times out at three seconds.

echo "What is your favorite song?"
echo "Quickly now, you only have $TMOUT seconds to answer!"
read song

if [ -z "$song" ]
then
  song="(no answer)"
  # Default response.
fi

echo "Your favorite song is $song."
```

There are other, more complex, ways of implementing timed input in a script. One alternative is to set up a timing loop to signal the script when it times out. This also requires a signal handling routine to [[debugging#^TRAPREF1|trap]] (see [[debugging#^EX76|Example 32-5]]) the interrupt generated by the timing loop (whew!).

**Example 9-2. Timed Input**

```bash
#!/bin/bash
# timed-input.sh

# TMOUT=3    Also works, as of newer versions of Bash.

TIMER_INTERRUPT=14
TIMELIMIT=3  # Three seconds in this instance.
             # May be set to different value.

PrintAnswer()
{
  if [ "$answer" = TIMEOUT ]
  then
    echo $answer
  else       # Don't want to mix up the two instances. 
    echo "Your favorite veggie is $answer"
    kill $!  #  Kills no-longer-needed TimerOn function
             #+ running in background.
             #  $! is PID of last job running in background.
  fi

}  


TimerOn()
{
  sleep $TIMELIMIT && kill -s 14 $$ &
  # Waits 3 seconds, then sends sigalarm to script.
}  


Int14Vector()
{
  answer="TIMEOUT"
  PrintAnswer
  exit $TIMER_INTERRUPT
}  

trap Int14Vector $TIMER_INTERRUPT
# Timer interrupt (14) subverted for our purposes.

echo "What is your favorite vegetable "
TimerOn
read answer
PrintAnswer


#  Admittedly, this is a kludgy implementation of timed input.
#  However, the "-t" option to "read" simplifies this task.
#  See the "t-out.sh" script.
#  However, what about timing not just single user input,
#+ but an entire script?

#  If you need something really elegant ...
#+ consider writing the application in C or C++,
#+ using appropriate library functions, such as 'alarm' and 'setitimer.'

exit 0
```

An alternative is using [[system#^STTYREF|stty]].

**Example 9-3. Once more, timed input**

```bash
#!/bin/bash
# timeout.sh

#  Written by Stephane Chazelas,
#+ and modified by the document author.

INTERVAL=5                # timeout interval

timedout_read() {
  timeout=$1
  varname=$2
  old_tty_settings=`stty -g`
  stty -icanon min 0 time ${timeout}0
  eval read $varname      # or just  read $varname
  stty "$old_tty_settings"
  # See man page for "stty."
}

echo; echo -n "What's your name? Quick! "
timedout_read $INTERVAL your_name

#  This may not work on every terminal type.
#  The maximum timeout depends on the terminal.
#+ (it is often 25.5 seconds).

echo

if [ ! -z "$your_name" ]  # If name input before timeout ...
then
  echo "Your name is $your_name."
else
  echo "Timed out."
fi

echo

# The behavior of this script differs somewhat from "timed-input.sh."
# At each keystroke, the counter resets.

exit 0
```

Perhaps the simplest method is using the -t option to [[internal-commands-and-builtins#^READREF|read]].

**Example 9-4. Timed _read_**

```bash
#!/bin/bash
# t-out.sh [time-out]
# Inspired by a suggestion from "syngin seven" (thanks).


TIMELIMIT=4         # 4 seconds

read -t $TIMELIMIT variable <&1
#                           ^^^
#  In this instance, "<&1" is needed for Bash 1.x and 2.x,
#  but unnecessary for Bash 3+.

echo

if [ -z "$variable" ]  # Is null?
then
  echo "Timed out, variable still unset."
else  
  echo "variable = $variable"
fi  

exit 0
```

$UID

User ID number

Current user's user identification number, as recorded in [[files#^DATAFILESREF1|/etc/passwd]]

This is the current user's real id, even if she has temporarily assumed another identity through [[system#^SUREF|su]]. $UID is a readonly variable, not subject to change from the command line or within a script, and is the counterpart to the [[system#^IDREF|id]] builtin.

**Example 9-5. Am I root?**

```bash
#!/bin/bash
# am-i-root.sh:   Am I root or not?

ROOT_UID=0   # Root has $UID 0.

if [ "$UID" -eq "$ROOT_UID" ]  # Will the real "root" please stand up?
then
  echo "You are root."
else
  echo "You are just an ordinary user (but mom loves you just the same)."
fi

exit 0


# ============================================================= #
# Code below will not execute, because the script already exited.

# An alternate method of getting to the root of matters:

ROOTUSER_NAME=root

username=`id -nu`              # Or...   username=`whoami`
if [ "$username" = "$ROOTUSER_NAME" ]
then
  echo "Rooty, toot, toot. You are root."
else
  echo "You are just a regular fella."
fi
```

See also [[starting-off-with-a-sha-bang#^EX2|Example 2-3]].

> [!note]
> The variables $ENV, $LOGNAME, $MAIL, $TERM, $USER, and $USERNAME are _not_ Bash [[internal-commands-and-builtins#^BUILTINREF|builtins]]. These are, however, often set as [[othertypesv#^ENVREF|environmental variables]] in one of the [[files#^FILESREF1|Bash]] or _login_ startup files. $SHELL, the name of the user's login shell, may be set from /etc/passwd or in an "init" script, and it is likewise not a Bash builtin.
>
> ```bash
> tcsh% echo $LOGNAME
> bozo
> tcsh% echo $SHELL
> /bin/tcsh
> tcsh% echo $TERM
> rxvt
> 
> bash$ echo $LOGNAME
> bozo
> bash$ echo $SHELL
> /bin/tcsh
> bash$ echo $TERM
> rxvt
> 	      
> ```

**Positional Parameters**

$0, $1, $2, etc.

Positional parameters, passed from command line to script, passed to a function, or [[internal-commands-and-builtins#^SETREF|set]] to a variable (see [[othertypesv#^EX17|Example 4-5]] and [[internal-commands-and-builtins#^EX34|Example 15-16]])

$#

Number of command-line arguments [[shell-wrapper#^EX4|^4] or positional parameters (see [Example 36-2]])

$*

All of the positional parameters, seen as a single word

> [!note] "$*" must be quoted.

$@

Same as $*, but each parameter is a quoted string, that is, the parameters are passed on intact, without interpretation or expansion. This means, among other things, that each parameter in the argument list is seen as a separate word.

> [!note] Of course, "$@" should be quoted.

**Example 9-6. _arglist_: Listing arguments with $* and $@**

```bash
#!/bin/bash
# arglist.sh
# Invoke this script with several arguments, such as "one two three" ...

E_BADARGS=85

if [ ! -n "$1" ]
then
  echo "Usage: `basename $0` argument1 argument2 etc."
  exit $E_BADARGS
fi  

echo

index=1          # Initialize count.

echo "Listing args with \"\$*\":"
for arg in "$*"  # Doesn't work properly if "$*" isn't quoted.
do
  echo "Arg #$index = $arg"
  let "index+=1"
done             # $* sees all arguments as single word. 
echo "Entire arg list seen as single word."

echo

index=1          # Reset count.
                 # What happens if you forget to do this?

echo "Listing args with \"\$@\":"
for arg in "$@"
do
  echo "Arg #$index = $arg"
  let "index+=1"
done             # $@ sees arguments as separate words. 
echo "Arg list seen as separate words."

echo

index=1          # Reset count.

echo "Listing args with \$* (unquoted):"
for arg in $*
do
  echo "Arg #$index = $arg"
  let "index+=1"
done             # Unquoted $* sees arguments as separate words. 
echo "Arg list seen as separate words."

exit 0
```

Following a **shift**, the $@ holds the remaining command-line parameters, lacking the previous $1, which was lost.

```bash
#!/bin/bash
# Invoke with ./scriptname 1 2 3 4 5

echo "$@"    # 1 2 3 4 5
shift
echo "$@"    # 2 3 4 5
shift
echo "$@"    # 3 4 5

# Each "shift" loses parameter $1.
# "$@" then contains the remaining parameters.
```

The $@ special parameter finds use as a tool for filtering input into shell scripts. The **cat "$@"** construction accepts input to a script either from stdin or from files given as parameters to the script. See [[textproc#^ROT13|Example 16-24]] and [[textproc#^CRYPTOQUOTE|Example 16-25]].

> [!caution] The $* and $@ parameters sometimes display inconsistent and puzzling behavior, depending on the setting of [[internal-variables#^IFSREF|$IFS]].

**Example 9-7. Inconsistent $* and $@ behavior**

```bash
#!/bin/bash

#  Erratic behavior of the "$*" and "$@" internal Bash variables,
#+ depending on whether or not they are quoted.
#  Demonstrates inconsistent handling of word splitting and linefeeds.


set -- "First one" "second" "third:one" "" "Fifth: :one"
# Setting the script arguments, $1, $2, $3, etc.

echo

echo 'IFS unchanged, using "$*"'
c=0
for i in "$*"               # quoted
do echo "$((c+=1)): [$i]"   # This line remains the same in every instance.
                            # Echo args.
done
echo ---

echo 'IFS unchanged, using $*'
c=0
for i in $*                 # unquoted
do echo "$((c+=1)): [$i]"
done
echo ---

echo 'IFS unchanged, using "$@"'
c=0
for i in "$@"
do echo "$((c+=1)): [$i]"
done
echo ---

echo 'IFS unchanged, using $@'
c=0
for i in $@
do echo "$((c+=1)): [$i]"
done
echo ---

IFS=:
echo 'IFS=":", using "$*"'
c=0
for i in "$*"
do echo "$((c+=1)): [$i]"
done
echo ---

echo 'IFS=":", using $*'
c=0
for i in $*
do echo "$((c+=1)): [$i]"
done
echo ---

var=$*
echo 'IFS=":", using "$var" (var=$*)'
c=0
for i in "$var"
do echo "$((c+=1)): [$i]"
done
echo ---

echo 'IFS=":", using $var (var=$*)'
c=0
for i in $var
do echo "$((c+=1)): [$i]"
done
echo ---

var="$*"
echo 'IFS=":", using $var (var="$*")'
c=0
for i in $var
do echo "$((c+=1)): [$i]"
done
echo ---

echo 'IFS=":", using "$var" (var="$*")'
c=0
for i in "$var"
do echo "$((c+=1)): [$i]"
done
echo ---

echo 'IFS=":", using "$@"'
c=0
for i in "$@"
do echo "$((c+=1)): [$i]"
done
echo ---

echo 'IFS=":", using $@'
c=0
for i in $@
do echo "$((c+=1)): [$i]"
done
echo ---

var=$@
echo 'IFS=":", using $var (var=$@)'
c=0
for i in $var
do echo "$((c+=1)): [$i]"
done
echo ---

echo 'IFS=":", using "$var" (var=$@)'
c=0
for i in "$var"
do echo "$((c+=1)): [$i]"
done
echo ---

var="$@"
echo 'IFS=":", using "$var" (var="$@")'
c=0
for i in "$var"
do echo "$((c+=1)): [$i]"
done
echo ---

echo 'IFS=":", using $var (var="$@")'
c=0
for i in $var
do echo "$((c+=1)): [$i]"
done

echo

# Try this script with ksh or zsh -y.

exit 0

#  This example script written by Stephane Chazelas,
#+ and slightly modified by the document author.
```

> [!note] The **$@** and **$*** parameters differ only when between double quotes.

**Example 9-8. $* and $@ when $IFS is empty**

```bash
#!/bin/bash

#  If $IFS set, but empty,
#+ then "$*" and "$@" do not echo positional params as expected.

mecho ()       # Echo positional parameters.
{
echo "$1,$2,$3";
}


IFS=""         # Set, but empty.
set a b c      # Positional parameters.

mecho "$*"     # abc,,
#                   ^^
mecho $*       # a,b,c

mecho $@       # a,b,c
mecho "$@"     # a,b,c

#  The behavior of $* and $@ when $IFS is empty depends
#+ on which Bash or sh version being run.
#  It is therefore inadvisable to depend on this "feature" in a script.


# Thanks, Stephane Chazelas.

exit
```

**Other Special Parameters**

$-

Flags passed to script (using [[internal-commands-and-builtins#^SETREF|set]]). See [[internal-commands-and-builtins#^EX34|Example 15-16]].

> [!caution] This was originally a _ksh_ construct adopted into Bash, and unfortunately it does not seem to work reliably in Bash scripts. One possible use for it is to have a script [[intandnonint#^IITEST|self-test whether it is interactive]].

$!

[[special-characters#^PROCESSIDDEF|PID]] (process ID) of last job run in background

```bash
LOG=$0.log

COMMAND1="sleep 100"

echo "Logging PIDs background commands for script: $0" >> "$LOG"
# So they can be monitored, and killed as necessary.
echo >> "$LOG"

# Logging commands.

echo -n "PID of \"$COMMAND1\":  " >> "$LOG"
${COMMAND1} &
echo $! >> "$LOG"
# PID of "sleep 100":  1506

# Thank you, Jacques Lederer, for suggesting this.
```

Using $! for job control:

```bash
possibly_hanging_job & { sleep ${TIMEOUT}; eval 'kill -9 $!' &> /dev/null; }
# Forces completion of an ill-behaved program.
# Useful, for example, in init scripts.

# Thank you, Sylvain Fourmanoit, for this creative use of the "!" variable.
```

Or, alternately:

```bash
# This example by Matthew Sage.
# Used with permission.

TIMEOUT=30   # Timeout value in seconds
count=0

possibly_hanging_job & {
        while ((count < TIMEOUT )); do
                eval '[ ! -d "/proc/$!" ] && ((count = TIMEOUT))'
                # /proc is where information about running processes is found.
                # "-d" tests whether it exists (whether directory exists).
                # So, we're waiting for the job in question to show up.
                ((count++))
                sleep 1
        done
        eval '[ -d "/proc/$!" ] && kill -15 $!'
        # If the hanging job is running, kill it.
}

#  -------------------------------------------------------------- #

#  However, this may not not work as specified if another process
#+ begins to run after the "hanging_job" . . .
#  In such a case, the wrong job may be killed.
#  Ariel Meragelman suggests the following fix.

TIMEOUT=30
count=0
# Timeout value in seconds
possibly_hanging_job & {

while ((count < TIMEOUT )); do
  eval '[ ! -d "/proc/$lastjob" ] && ((count = TIMEOUT))'
  lastjob=$!
  ((count++))
  sleep 1
done
eval '[ -d "/proc/$lastjob" ] && kill -15 $lastjob'

}

exit
```

$_

Special variable set to final argument of previous command executed.

**Example 9-9. Underscore variable**

```bash
#!/bin/bash

echo $_              #  /bin/bash
                     #  Just called /bin/bash to run the script.
                     #  Note that this will vary according to
                     #+ how the script is invoked.

du >/dev/null        #  So no output from command.
echo $_              #  du

ls -al >/dev/null    #  So no output from command.
echo $_              #  -al  (last argument)

:
echo $_              #  :
```

$?

[[exit-status#^EXITSTATUSREF|Exit status]] of a command, [[functions#^FUNCTIONREF|function]], or the script itself (see [[complexfunct#^MAX|Example 24-7]])

`$$`

Process ID (_PID_) of the script itself. [[debugging#^ONLINE|^5] The $$ variable often finds use in scripts to construct "unique" temp file names (see [Example 32-6]], [[filearchiv#^DERPM|Example 16-31]], and [[job-control-commands#^SELFDESTRUCT|Example 15-27]]). This is usually simpler than invoking [[filearchiv#^MKTEMPREF|mktemp]].

[^1]: A _stack register_ is a set of consecutive memory locations, such that the values stored (_pushed_) are retrieved (_popped_) in _reverse_ order. The last value stored is the first retrieved. This is sometimes called a _LIFO_ (_last-in-first-out_) or _pushdown_ stack.

[^2]: The PID of the currently running script is `$$`, of course.

[^3]: Somewhat analogous to [[localvar#^RECURSIONREF|recursion]], in this context _nesting_ refers to a pattern embedded within a larger pattern. One of the definitions of _nest_, according to the 1913 edition of _Webster's Dictionary_, illustrates this beautifully: "_A collection of boxes, cases, or the like, of graduated size, each put within the one next larger._"

[^4]: The words "argument" and "parameter" are often used interchangeably. In the context of this document, they have the same precise meaning: _a variable passed to a script or function._

[^5]: Within a script, inside a subshell, `$$` [[internal-variables#^BASHPIDREF|returns the PID of the script]], not the subshell.
