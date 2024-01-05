# Index

This index / glossary / quick-reference lists many of the important topics covered in the text. Terms are arranged in _approximate_ ASCII sorting order, _modified as necessary_ for enhanced clarity.

Note that _commands_ are indexed in [[part4#^PART4A|Part 4]].

* * *

**^** (caret)

- [[special-characters#^BEGLINEREF|Beginning-of-line]], in a [[regexp#^REGEXREF|Regular Expression]]
    
- **^**
    
    **^^**
    
    [[bash-ver4#^CASEMODPARAMSUB|Uppercase conversion]] in _parameter substitution_
    

**~** _Tilde_

- **~** [[special-characters#^TILDEREF|home directory]], corresponds to [[internal-variables#^HOMEDIRREF|$HOME]]
    
- **~/** [[special-characters#^TILDEREF|_Current user's_ home directory]]
    
- **~+** [[special-characters#^WORKINGDIRREF|_Current_ working directory]]
    
- **~-** [[special-characters#^PREVWORKINGDIR|_Previous_ working directory]]
    

**=** _Equals_ sign

- **=** [[varassignment#^EQREF|Variable assignment]] operator
    
- **=** [[other-comparison-operators#^SCOMPARISON1|String comparison]] operator
    
    **==** [[other-comparison-operators#^SCOMPARISON2|String comparison]] operator
    
- **=~** _Regular Expression_ [[bash-ver3#^REGEXMATCHREF|match]] operator
    
    [[contributed-scripts#^FINDSPLIT0|_Example script_]]
    

**<** Left angle bracket

- Is-less-than
    
    [[other-comparison-operators#^LTREF|String comparison]]
    
    [[other-comparison-operators#^INTLT|Integer comparison]] within [[double-parentheses-construct|double parentheses]]
    
- Redirection
    
    **<** [[io-redirection#^IOREDIRECTIONREF2|stdin]]
    
    **<<** [[special-characters#^HEREDOCRRREF|_Here document_]]
    
    **<<<** [[special-characters#^HERESTRINGREF|_Here string_]]
    
    **<>** [[special-characters#^REDIRRW|Opening a file]] for _both_ reading and writing
    

**>** Right angle bracket

- Is-greater-than
    
    [[other-comparison-operators#^GTREF|String comparison]]
    
    [[other-comparison-operators#^INTGT|Integer comparison]], within _double parentheses_
    
- Redirection
    
    **>** [[io-redirection#^IOREDIRECTIONREF|Redirect stdout]] to a file
    
    **>>** [[io-redirection#^IOREDIRECTIONREF|Redirect stdout]] to a file, but _append_
    
    **i>&j** [[io-redirection#^IOREDIRECTIONREF1|Redirect _file descriptor_ i]] to _file descriptor_ j
    
    **>&j** [[io-redirection#^IOREDIRECTIONREF1|Redirect stdout]] to _file descriptor_ j
    
    **>&2** [[special-characters#^REDIROUTERROR2|Redirect stdout]] of a command to stderr
    
    **2>&1** [[io-redirection#^IOREDIRECTIONREF1|Redirect stderr]] to stdout
    
    **&>** [[special-characters#^REDIROUTERROR|Redirect _both_ stdout and stderr]] of a command to a file
    
    **:> file** [[io-redirection#^IOREDIRECTIONREF|Truncate file]] to zero length
    

**|** [[special-characters#^PIPEREF|Pipe]], a device for passing the output of a command to another command or to the shell

**||** [[operators#^ORREF|Logical OR test operator]]

**-** (dash)

- [[parameter-substitution#^DEFPARAM1|Prefix to _default parameter_]], in _parameter substitution_
    
- [[special-characters#^DASHREF|Prefix to _option flag_]]
    
- [[special-characters#^DASHREF2|Indicating _redirection_]] from stdin or stdout
    
- **--** (double-dash)
    
    [[special-characters#^DOUBLEDASHREF|Prefix to _long_ command options]]
    
    [[double-parentheses-construct#^PLUSPLUSREF|_C-style_ variable decrement]] within [[double-parentheses-construct#^DBLPARENSREF|double parentheses]]
    

**;** (semicolon)

- [[special-characters#^SEMICOLONREF|As command separator]]
    
- **\;** [[moreadv#^FINDREF0|_Escaped_ semicolon]], terminates a [[moreadv#^FINDREF|find]] command
    
- **;;** [[special-characters#^DOUBLESEMICOLON|Double-semicolon]], terminator in a [[testbranch#^CASEESAC1|case]] option
    
    Required when ...
    
    [[loops#^NEEDSEMICOLON|_do_ keyword is on the first line of _loop_]]
    
    [[gotchas#^OMITSEMICOLON|terminating _curly-bracketed_ code block]]
    
- **;;&** **;&** [[bash-ver4#^NCTERM|Terminators]] in a _case_ option ([[bash-ver4#^BASH4REF|version 4+]] of Bash).
    

**:** Colon

- **:> filename** [[io-redirection#^IOREDIRECTIONREF|Truncate file]] to zero length
    
- [[special-characters#^NULLREF|_null_ command]], equivalent to the [[internal#^TRUEREF|true]] Bash builtin
    
- Used in an [[here-docs#^ANONHEREDOC0|anonymous here document]]
    
- Used in an [[special-characters#^COLONINFUNCTION|otherwise empty function]]
    
- Used as a [[functions#^FSTRANGEREF|function name]]
    

**!** [[special-characters#^NOTREF|Negation operator]], inverts [[exit-status#^NEGCOND|exit status]] of a test or command

- **!=** [[other-comparison-operators#^NOTEQUAL|not-equal-to]] String comparison operator
    

**?** (question mark)

- [[x17129#^QUEXREGEX|Match zero or one characters]], in an [[x17129#^EXTREGEX|Extended Regular Expression]]
    
- [[special-characters#^QUEXWC|Single-character _wild card_]], in [[globbingref|globbing]]
    
- In a [[special-characters#^CSTRINARY|_C_-style Trinary operator]]
    

**//** [[internal#^DOUBLESLASHREF|Double forward slash]], behavior of [[internal#^CDREF|cd]] command toward

**.** (dot / period)

- **.** [[special-characters#^DOTREF|Load a file]] (into a script), equivalent to [[internal#^SOURCEREF|source]] command
    
- **.** [[x17129#^REGEXDOT|Match single character]], in a [[regexp#^REGEXREF|Regular Expression]]
    
- **.** [[special-characters#^DOTDIRECTORY|Current working directory]]
    
    **./** [[internal-variables#^CURRENTWDREF|Current working directory]]
    
- **..** [[special-characters#^DOTDIRECTORY|_Parent_ directory]]
    

**' ... '** (single quotes) [[varsubn#^SNGLQUO|_strong_ quoting]]

**" ... "** (double quotes) [[varsubn#^DBLQUO|_weak_ quoting]]

- [[quoting-variables#^QUOTINGBSL|_Double-quoting_ the _backslash_ (**\**) character]]
    

**,**

- [[operators#^COMMAOP|Comma operator]]
    
- **,**
    
    **,,**
    
    [[bash-ver4#^CASEMODPARAMSUB|Lowercase conversion]] in _parameter substitution_
    

**()** Parentheses

- **( ... )** [[special-characters#^PARENSREF|Command group]]; starts a [[subshells#^SUBSHELLSREF|subshell]]
    
- **( ... )** [[x17129#^PARENGRPS|Enclose group]] of _Extended Regular Expressions_
    
- **>( ... )**
    
    **<( ... )** [[Chapter 23. Process Substitution#^PROCESSSUBREF|Process substitution]]
    
- **... )** [[testbranch#^CASEPAREN|Terminates test-condition]] in _case_ construct
    
- **(( ... ))** [[double-parentheses-construct#^DBLPARENSREF|Double parentheses]], in arithmetic expansion
    

**[[special-characters#^LEFTBRACKET|** [Left bracket]], _test_ construct

**[ ]**Brackets

- [[Chapter 27. Arrays#^BRACKARRAY|_Array_ element]]
    
- [[x17129#^BRACKETSREF|Enclose character set to match]] in a _Regular Expression_
    
- [[special-characters#^BRACKTEST|_Test_ construct]]
    

**[[test-constructs#^DBLBRACKETS|[ ... ]]** [Double brackets]], extended _test_ construct

**$** [[x17129#^DOLLARSIGNREF|_Anchor_]], in a [[regexp#^REGEXREF|Regular Expression]]

**$** [[varsubn|Prefix to a variable name]]

**$( ... )** [[varassignment#^COMMANDSUBREF0|Command substitution]], setting a variable with output of a command, using parentheses notation

**` ... `** [[commandsub#^BACKQUOTESREF|Command substitution]], using [[special-characters#^BACKTICKSREF|backquotes]] notation

**$[[special-characters#^BRACKETARITH| ... ]** [Integer expansion]] (deprecated)

**${ ... }** Variable manipulation / evaluation

- **${var}** [[parameter-substitution#^PSSUB1|Value of a variable]]
    
- **${#var}** [[parameter-substitution#^PSOREX1|Length of a variable]]
    
- **${#@}**
    
    **${#*}** [[parameter-substitution#^NUMPOSPARAM|Number of _positional parameters_]]
    
- **${parameter?err_msg}** [[parameter-substitution#^QERRMSG|Parameter-unset message]]
    
- **${parameter-default}**
    
    **${parameter:-default}**
    
    **${parameter=default}**
    
    **${parameter:=default}** [[parameter-substitution#^DEFPARAM1|Set default parameter]]
    
- **${parameter+alt_value}**
    
    **${parameter:+alt_value}**
    
    [[parameter-substitution#^PARAMALTV|Alternate value]] of parameter, if set
    
- **${!var}**
    
    [[ivr#^IVR2|Indirect referencing of a variable]], new notation
    
- **${!#}**
    
    [[othertypesv#^LASTARGREF|Final _positional parameter_]]. (This is an _indirect reference_ to [[internal-variables#^CLACOUNTREF|$#]].)
    
- **${!varprefix*}**
    
    **${!varprefix@}**
    
    [[parameter-substitution#^VARPREFIXM|Match _names_]] of all previously declared variables beginning with varprefix
    
- **${string:position}**
    
    **${string:position:length}** [[manipulating-strings#^SUBSTREXTR01|Substring extraction]]
    
- **${var#Pattern}**
    
    **${var##Pattern}** [[parameter-substitution#^PSOREX2|Substring removal]]
    
- **${var%Pattern}**
    
    **${var%%Pattern}** [[parameter-substitution#^PCTPATREF|Substring removal]]
    
- **${string/substring/replacement}**
    
    **${string//substring/replacement}**
    
    **${string/#substring/replacement}**
    
    **${string/%substring/replacement}** [[manipulating-strings#^SUBSTRREPL00|Substring replacement]]
    

**$' ... '** [[escaping#^STRQ|String expansion]], using _escaped_ characters.

**\** [[escaping#^ESCP|Escape]] the character following

- **\< ... \>** [[x17129#^ANGLEBRAC|Angle brackets]], _escaped_, word boundary in a [[regexp#^REGEXREF|Regular Expression]]
    
- **\{ N \}** [[x17129#^ESCPCB|"Curly" brackets]], _escaped_, number of character sets to match in an [[x17129#^EXTREGEX|Extended RE]]
    
- **\;** [[moreadv#^FINDREF0|_Semicolon_]], _escaped_, terminates a [[moreadv#^FINDREF|find]] command
    
- **\$$** [[ivr#^IVRREF|Indirect reverencing of a variable]], old-style notation
    
- [[escaping#^ESCNEWLINE|Escaping a _newline_]], to write a multi-line command
    

**&**

- **&>** [[special-characters#^REDIROUTERROR|Redirect _both_ stdout and stderr]] of a command to a file
    
- **>&j** [[io-redirection#^IOREDIRECTIONREF1|Redirect stdout]] to _file descriptor_ _j_
    
    **>&2** [[special-characters#^REDIROUTERROR2|Redirect stdout]] of a command to stderr
    
- **i>&j** [[io-redirection#^IOREDIRECTIONREF1|Redirect _file descriptor_]] _i_ to _file descriptor_ _j_
    
    **2>&1** [[io-redirection#^IOREDIRECTIONREF1|Redirect stderr]] to stdout
    
- [[io-redirection#^CFD|Closing _file descriptors_]]
    
    **n<&-** Close input file descriptor _n_
    
    **0<&-**, **<&-** Close stdin
    
    **n>&-** Close output file descriptor _n_
    
    **1>&-**, **>&-** Close stdout
    
- **&&** [[special-characters#^LOGICALAND|Logical AND test operator]]
    
- **Command &** [[special-characters#^BGJOB|Run job in _background_]]
    

**#** [[special-characters#^HASHMARKREF|Hashmark]], special symbol beginning a script _comment_

**#!** [[starting-off-with-a-sha-bang#^SHABANGREF|Sha-bang]], special string starting a [[Part 1. Introduction#^WHATSASCRIPT|shell script]]

***** Asterisk

- [[special-characters#^ASTERISKREF|_Wild card_]], in [[globbingref|globbing]]
    
- [[special-characters#^ASTERISKREF2|Any number of characters]] in a [[regexp#^REGEXREF|Regular Expression]]
    
- ****** [[operators#^EXPONENTIATIONREF|Exponentiation]], arithmetic operator
    
- ****** Extended _globbing_ [[bash-ver4#^GLOBSTARREF|file-match operator]]
    

**%** Percent sign

- [[operators#^MODULOREF|Modulo]], division-remainder arithmetic operation
    
- [[parameter-substitution#^PCTPATREF|Substring removal]] (pattern matching) operator
    

**+** Plus sign

- [[x17129#^PLUSREF|_Character match_]], in an [[x17129#^EXTREGEX|extended Regular Expression]]
    
- [[parameter-substitution#^PARAMALTV|Prefix to _alternate parameter_]], in _parameter substitution_
    
- **++** [[double-parentheses-construct#^PLUSPLUSREF|_C-style_ variable increment]], within [[double-parentheses-construct#^DBLPARENSREF|double parentheses]]
    

* * *

_Shell Variables_

**$_** [[internal-variables#^UNDERSCOREREF|Last argument to previous command]]

**$-** [[internal-variables#^FLPREF|Flags passed to script]], using [[internal#^SETREF|set]]

**$!** [[internal-variables#^PIDVARREF|_Process ID_ of last background job]]

**$?** [[exit-status#^EXSREF|_Exit status_ of a command]]

**$@** All the _positional parameters_, [[internal-variables#^APPREF2|as _separate_ words]]

**$*** All the _positional parameters_, [[internal-variables#^APPREF|as a _single_ word]]

**$$** [[special-characters#^PROCESSIDREF|Process ID]] of the script

**$#** [[internal-variables#^CLACOUNTREF|Number of arguments passed]] to a [[functions#^FUNCTIONREF|function]], or to the script itself

**$0** [[othertypesv#^SCRNAMEPARAM|Filename of the script]]

**$1** [[othertypesv#^POSPARAMREF1|First argument passed to script]]

**$9** [[othertypesv#^POSPARAMREF1|Ninth argument passed to script]]

[[refcards#^SPECSHVARTAB|**Table**]] of _shell variables_

* * * * * *

**-a** [[other-comparison-operators#^COMPOUNDAND|Logical AND]] compound comparison test

Address database, [[testbranch#^EX30|script example]]

_Advanced Bash Scripting Guide_, [[mirrorsites#^WHERE_TARBALL|where to download]]

[[Chapter 25. Aliases#^ALIASREF|Alias]]

- [[Chapter 25. Aliases#^UNALIASREF|Removing an _alias_]], using _unalias_
    

[[commandsub#^AGRAM2|Anagramming]]

[[list-cons#^LCONS1|_And_ list]]

- [[list-cons#^ANDDEFAULT|To supply default command-line argument]]
    

[[operators#^LOGOPS1|_And_ logical operator]] **&&**

[[x17129#^ANGLEBRAC|Angle brackets]], _escaped_, **\< . . . \>** word boundary in a [[regexp#^REGEXREF|Regular Expression]]

[[here-docs#^ANONHEREDOC0|Anonymous _here document_]], using **:**

[[filearchiv#^FAARCHIVING1|Archiving]]

- [[filearchiv#^RPMREF|rpm]]
    
- [[filearchiv#^TARREF|tar]]
    

[[Chapter 13. Arithmetic Expansion#^ARITHEXPREF|Arithmetic expansion]]

- [[test-constructs#^ARXS|_exit status_ of]]
    
- [[Chapter 13. Arithmetic Expansion#^ARITHEXPVAR1|variations of]]
    

[[operators#^AROPS1|Arithmetic operators]]

- [[operators#^ARITHOPSCOMB|combination operators]], _C_-style
    
    **+=** **-=** ***=** **/=** **%=**
    
    |   |   |
    |---|---|
    |![[../images/note.gif|Note]]|[[bashver3#^PLUSEQSTR|In certain contexts]], **+=** can also function as a _string concatenation_ operator.|
    

[[Chapter 27. Arrays#^ARRAYREF|Arrays]]

- [[bash-ver4#^ASSOCARR|Associative arrays]]
    
    [[optimizations#^ASSOCARRTST|more efficient]] than conventional arrays
    
- [[Chapter 27. Arrays#^ARRAYREF|Bracket notation]]
    
- [[Chapter 27. Arrays#^ARRAYAPPEND0|Concatenating]], _example script_
    
- [[Chapter 27. Arrays#^COPYARRAY0|Copying]]
    
- [[typing-variables#^ARRAYDECLARE|Declaring]]
    
    declare -a array_name
    
- [[Chapter 27. Arrays#^ARRAYINDIR|Embedded arrays]]
    
- [[Chapter 27. Arrays#^EMPTYARRAY0|Empty arrays, empty elements]], _example script_
    
- [[Chapter 27. Arrays#^ARRAYINDIR|Indirect references]]
    
- [[Chapter 27. Arrays#^ARRAYINIT0|Initialization]]
    
    array=( element1 element2 ... elementN)
    
    [[Chapter 27. Arrays#^ARRAYASSIGN0|_Example script_]]
    
    Using [[Chapter 27. Arrays#^ARRAYINITCS|command substitution]]
    
- [[Chapter 27. Arrays#^ARRAYINITCS|Loading a file]] into an array
    
- [[Chapter 27. Arrays#^ARRAYMULTIDIM|Multidimensional]], simulating
    
- [[Chapter 27. Arrays#^ARRAYNEST|Nesting and embedding]]
    
- [[Chapter 27. Arrays#^ARRAYNOTATION|Notation and usage]]
    
- [[Chapter 27. Arrays#^ARRAYNUMELEMENTS|Number of elements in]]
    
    ${#array_name[@]}
    
    ${#array_name[*]}
    
- [[Chapter 27. Arrays#^ARRAYSYNTAX|Operations]]
    
- [[assorted-tips#^PASSARRAY|Passing an _array_]] to a function
    
- As [[assorted-tips#^RETARRAY|_return value_ from a function]]
    
- Special properties, [[Chapter 27. Arrays#^ARRAYSPECIALPROPS|example script]]
    
- String operations, [[Chapter 27. Arrays#^ARRAYSTRINGOPS|example script]]
    
- [[Chapter 27. Arrays#^ARRAYUNSET|_unset_ deletes array elements]]
    

[[internal#^READARROW|Arrow keys]], detecting

ASCII

- [[special-characters#^ASCIIDEF|Definition]]
    
- [[Appendix T. ASCII Table|Scripts for generating ASCII table]]
    

[[C.2. Awk|C.2. Awk]] field-oriented text processing language

- [[generate-random-integer#^AWKRANDOMREF|rand()]], random function
    
- [[manipulating-strings#^AWKSTRINGMANIP2|String manipulation]]
    
- [[internal#^EXPORTAWK|Using _export_]] to pass a variable to an embedded _awk_ script
    

* * *

Backlight, [[system#^BACKLIGHT|setting the brightness]]

[[special-characters#^BACKTICKSREF|Backquotes]], used in [[commandsub#^BACKQUOTESREF|command substitution]]

[[mathc#^BASE0|Base conversion]], _example script_

[[shell-programming#^BASHDEF|Bash]]

- [[gotchas#^BASH3GOTCHA|Bad scripting practices]]
    
- [[contributed-scripts#^BASICSREV0|Basics reviewed]], _script example_
    
- [[G.2. Bash Command-Line Options#^CLOPTS|Command-line options]]
    
    [[options#^OPTIONSTABLE|**Table**]]
    
- [[portabilityissues#^BASHCOMPAT|Features that classic _Bourne_ shell lacks]]
    
- [[internal-variables|Internal variables]]
    
- [[bash-ver2#^BASH2REF|Version 2]]
    
- [[bash-ver3#^BASH3REF|Version 3]]
    
- [[bash-ver4#^BASH4REF|Version 4]]
    
    [[bash-ver4#^BASH41|Version 4.1]]
    
    [[bash-ver4#^BASH42|Version 4.2]]
    

[[sample-bashrc|.bashrc]]

[[internal-variables#^BASHSUBSHELLREF|$BASH_SUBSHELL]]

[[basic-commands#^BASICCOMMANDS1|Basic commands]], external

[[Appendix N. Converting DOS Batch Files to Shell Scripts#^DOSBATCH1|Batch files]], _DOS_

[[timedate#^BATCHPROCREF|Batch processing]]

[[mathc#^BCREF|bc]], calculator utility

- [[mathc#^BCHEREDOC|In a _here document_]]
    
- [[mathc#^BCTEMPLATE|Template]] for calculating a script variable
    

[[bibliography|bibliography]]

[[textproc#^BISONREF|Bison]] utility

[[operators#^BITWSOPS1|Bitwise operators]]

- [[contributed-scripts#^BASE64|Example script]]
    

[[devref1#^BLOCKDEVREF|Block devices]]

- [[file-test-operators#^BLOCKDEVTEST|testing for]]
    

[[special-characters#^CODEBLOCKREF|Blocks of code]]

- [[loops#^NODODONE|Iterating / looping]]
    
- [[special-characters#^BLOCKIO|Redirection]]
    
    _Script example_: [[special-characters#^BLOCKIO2|Redirecting output of a a code block]]
    

[[extmisc#^BFS|Bootable flash drives]], creating

[[special-characters#^BRACEEXPREF|Brace expansion]]

- [[special-characters#^BRACEEXPREF33|Extended]], _{a..z}_
    
- [[bash-ver3#^BRACEEXPREF3|Parameterizing]]
    
- With [[bash-ver4#^BRACEEXPREF4|increment and zero-padding]] (new feature in Bash, [[bash-ver4#^BASH4REF|version 4]])
    

Brackets, **[ ]**

- [[Chapter 27. Arrays#^BRACKARRAY|_Array_ element]]
    
- [[x17129#^BRACKETSREF|Enclose character set to match]] in a _Regular Expression_
    
- [[special-characters#^BRACKTEST|_Test_ construct]]
    

Brackets, _curly_, **{}**, used in

- [[special-characters#^CODEBLOCKREF|Code block]]
    
- [[moreadv#^CURLYBRACKETSREF|_find_]]
    
- [[x17129#^ESCPCB|_Extended Regular Expressions_]]
    
- [[othertypesv#^BRACKETNOTATION|_Positional parameters_]]
    
- [[moreadv#^XARGSCURLYREF|_xargs_]]
    

[[loop-control#^BRKCONT1|break]] _loop_ control command

- [[loop-control#^BREAKPARAM|Parameter]] (optional)
    

[[internal#^BUILTINREF|Builtins]] in _Bash_

- [[internal#^BLTINFRK|Do not fork a subprocess]]
    

* * *

[[testbranch#^CASEESAC1|_case_ construct]]

- [[testbranch#^CASECL|Command-line parameters]], handling
    
- [[testbranch#^CSGLOB|Globbing]], filtering strings with
    

[[basic-commands#^CATREF|cat]], con_cat_entate file(s)

- [[optimizations#^CATABUSE|Abuse of]]
    
- [[here-docs#^CATSCRIPTREF|_cat_ scripts]]
    
- [[basic-commands#^CATLESSEFF|Less efficient than redirecting stdin]]
    
- [[internal#^READPIPEREF|Piping the output of]], to a [[internal#^READREF|read]]
    
- [[basic-commands#^CATUSES|Uses of]]
    

[[devref1#^CHARDEVREF|Character devices]]

- [[file-test-operators#^CHARDEVTEST|testing for]]
    

[[filearchiv#^CHECKSUMREF|Checksum]]

[[othertypesv#^CHILDREF|Child processes]]

[[special-characters#^NULLREF|Colon]], **:** , equivalent to the [[internal#^TRUEREF|true]] Bash builtin

[[colorizing#^COLORIZINGREF|Colorizing scripts]]

- Cycling through the background colors, [[contributed-scripts#^SHOWALLC|example script]]
    
- [[colorizing#^COLORIZTABLE|**Table**]] of color escape sequences
    
- [[colorizing#^COLORIZTEMPL|Template]], colored text on colored background
    

[[operators#^COMMAOP|Comma operator]], linking commands or operations

[[G.2. Bash Command-Line Options|Command-line options]]

[[bash-ver4#^CNFH|command_not_found_handle ()]] _builtin_ error-handling function ([[bash-ver4#^BASH4REF|version 4+]] of Bash)

[[commandsub#^COMMANDSUBREF|Command substitution]]

- [[commandsub#^CSPARENS|**$( ... )**]], preferred notation
    
- [[commandsub#^BACKQUOTESREF|_Backquotes_]]
    
- [[commandsub#^CSTOOLSET|Extending the _Bash_ toolset]]
    
- [[commandsub#^CSSUBSH|Invokes a _subshell_]]
    
- [[commandsub#^CSNEST|Nesting]]
    
- [[commandsub#^CSTRNL|Removes trailing newlines]]
    
- [[commandsub#^CSVL|Setting variable from loop output]]
    
- [[commandsub#^CSWS|Word splitting]]
    

[[assorted-tips#^COMMENTH|Comment headers]], special purpose

Commenting out blocks of code

- Using an [[here-docs#^CBLOCK1|_anonymous_ here document]]
    
- Using an [[assorted-tips#^COMOUTBL|_if-then_ construct]]
    

[[communications|Communications and hosts]]

[[other-comparison-operators#^CCOMPARISON1|Compound comparison]] operators

[[filearchiv#^FACOMPRESSION1|Compression utilities]]

- [[filearchiv#^BZIPREF|bzip2]]
    
- [[filearchiv#^COMPRESSREF|compress]]
    
- [[filearchiv#^GZIPREF|gzip]]
    
- [[filearchiv#^ZIPREF|zip]]
    

[[loop-control#^BRKCONT1|continue]] loop control command

[[special-characters#^CONTROLCHARREF|Control characters]]

- [[special-characters#^CTLCREF|Control-C]], _break_
    
- [[special-characters#^CTLDREF|Control-D]], terminate / log out / erase
    
- [[special-characters#^CTLGREF|Control-G]], **BEL** (_beep_)
    
- [[special-characters#^CTLHREF|Control-H]], _rubout_
    
- [[special-characters#^CTLJREF|Control-J]], _newline_
    
- [[special-characters#^CTLMREF|Control-M]], carriage return
    

[[bash-ver4#^COPROCREF|Coprocesses]]

[[system#^CRONREF|cron]], scheduling _daemon_

[[assorted-tips#^CSTYLE|_C_-style syntax]] , for handling variables

[[textproc#^CWSOLVER|Crossword puzzle solver]]

[[contributed-scripts#^GRONSFELD|Cryptography]]

Curly brackets {}

- [[moreadv#^CURLYBRACKETSREF|in _find_ command]]
    
- [[x17129#^ESCPCB|in an _Extended Regular Expression_]]
    
- [[moreadv#^XARGSCURLYREF|in _xargs_]]
    

* * *

[[communications#^DAEMONREF|Daemons]], in UNIX-type OS

[[timedate#^DATEREF|date]]

[[mathc#^DCREF|dc]], calculator utility

[[extmisc#^DDREF|dd]], _data duplicator_ command

- [[extmisc#^DDCONVERSIONS|Conversions]]
    
- [[extmisc#^DDCOPY|Copying raw data]] to/from devices
    
- [[extmisc#^DDFDEL|File deletion]], _secure_
    
- [[extmisc#^DDKEYSTROKES|Keystrokes]], capturing
    
- [[extmisc#^DDOPTIONS|Options]]
    
- [[extmisc#^DDRANDOM|Random access]] on a data stream
    
- _Raspberry Pi_, [[extmisc#^RPSDCARD01|script for preparing a bootable SD card]]
    
- [[extmisc#^DDSWAP|Swapfiles]], initializing
    
- [[bibliography#^DDLINK|Thread on _www.linuxquestions.org_]]
    

[[debugging|Debugging scripts]]

- [[debugging#^DEBUGTOOLS|Tools]]
    
- [[debugging#^DEBUGTRAP|_Trapping_ at exit]]
    
- [[debugging#^TRAPREF1|_Trapping_ signals]]
    

[[numerical-constants#^NUMCONSTANTS|Decimal number]], Bash interprets numbers as

[[typing-variables#^DECLARE1REF|declare]] builtin

- [[typing-variables#^DECLAREOPSREF1|options]]
    
    [[bash-ver4#^DECLARECASEMOD|case-modification]] options ([[bash-ver4#^BASH4REF|version 4+]] of Bash)
    

[[parameter-substitution#^DEFPARAM|Default parameters]]

[[devproc#^DEVPROCREF|/dev]] directory

- [[Chapter 31. Of Zeros and Nulls#^DEVNULLREF|/dev/null]] pseudo-device file
    
- [[generate-random-integer#^URANDOMREF|/dev/urandom]] pseudo-device file, generating pseudorandom numbers with
    
- [[Chapter 31. Of Zeros and Nulls#^ZEROSREF1|/dev/zero]], pseudo-device file
    

[[devref1#^DEVFILEREF|Device file]]

[[assorted-tips#^DIALOGREF|_dialog_]], utility for generating _dialog_ boxes in a script

[[internal-variables#^DIRSTACKREF|$DIRSTACK]] _directory stack_

[[restricted-sh#^DISABLEDCOMMREF|Disabled commands]], in _restricted shells_

[[loops#^DOINREF|do]] keyword, begins execution of commands within a [[loops-and-branches#^LOOPREF00|loop]]

[[loops#^DOINREF|done]] keyword, terminates a loop

[[Appendix N. Converting DOS Batch Files to Shell Scripts#^DOSBATCH1|_DOS_ batch files]], converting to shell scripts

[[Appendix N. Converting DOS Batch Files to Shell Scripts#^DOSUNIXEQUIV|_DOS_ commands]], UNIX equivalents of (**table**)

[[basic-commands#^DOTFILESREF|_dot files_]], "hidden" setup and configuration files

[[test-constructs#^DBLBRACKETS|Double brackets]] **[[tests#^IFTHEN|[ ... ]]** [test]] construct

- and [[test-constructs#^DBLBRAEV|evaluation of _octal/hex_ constants]]
    

[[double-parentheses-construct#^DBLPARENSREF|Double parentheses]] **(( ... ))** arithmetic expansion/evaluation construct

[[varsubn#^DBLQUO|Double quotes]] **" ... "** _weak_ quoting

- [[quoting-variables#^QUOTINGBSL|_Double-quoting_ the _backslash_ (**\**) character]]
    

[[C.1. Sed#^DOUBLESPACE|Double-spacing a text file]], using [[Appendix C. A Sed and Awk Micro-Primer#^SEDREF|sed]]

* * *

**-e** [[file-test-operators#^RTIF|File exists]] test

[[internal#^ECHOREF|echo]]

- [[internal#^ECHOGREPREF|Feeding commands down a _pipe_]]
    
- [[internal#^ECHOCS|Setting a variable]] using [[commandsub#^COMMANDSUBREF|command substitution]]
    
- [[internal#^BINECHO|/bin/echo]], external _echo_ command
    

[[test-constructs#^ELIFREF1|elif]], Contraction of _else_ and [[tests#^IFTHEN|if]]

[[test-constructs#^ELSEREF|else]]

Encrypting files, using [[filearchiv#^OPENSSLREF|openssl]]

[[testbranch#^CASEESAC1|esac]], keyword terminating _case_ construct

[[othertypesv#^ENVREF|_Environmental_ variables]]

[[other-comparison-operators#^EQUALREF|-eq]] , _is-equal-to_ [[other-comparison-operators#^ICOMPARISON1|integer comparison]] test

[[Chapter 27. Arrays#^PRIMES0|Eratosthenes, Sieve of]], algorithm for generating prime numbers

[[escaping#^SPM|Escaped characters]], special meanings of

- Within [[escaping#^STRQ|$' ... ']] string expansion
    
- [[bash-ver4#^UNICODEREF2|Used with _Unicode_ characters]]
    

[[system#^FSTABREF|/etc/fstab]] (filesystem mount) file

[[files#^DATAFILESREF1|/etc/passwd]] (user account) file

[[internal-variables#^EUIDREF|$EUID]], _Effective user ID_

[[internal#^EVALREF|eval]], Combine and _evaluate_ expression(s), with variable expansion

- [[internal#^EVALEFF|Effects of]], _Example script_
    
- [[internal#^EVALFORCED|Forces _reevaluation_]] of arguments
    
- And [[ivr#^EVALINDREF|indirect references]]
    
- [[internal#^EVALRISK|Risk of using]]
    
- [[contributed-scripts#^SAMORSE|Using _eval_ to convert _array_ elements into a command list]]
    
- [[internal#^ARRCHOICE0|Using _eval_ to select among variables]]
    

[[test-constructs#^DBLBRAEV|Evaluation of _octal/hex_ constants within [[ ... ]]]]

[[x17974#^USINGEXECREF|exec]] command, using in [[io-redirection#^IOREDIRREF|redirection]]

[[exercises|Exercises]]

Exit and Exit status

- [[exit-status#^EXITCOMMANDREF|exit]] command
    
- [[exit-status#^EXITSTATUSREF|Exit status]] (_exit code_, _return_ status of a command)
    
    [[exitcodes#^EXITCODESREF|**Table**]], _Exit codes_ with special meanings
    
    [[gotchas#^GOTCHAEXITVALANAMALIES|Anomalous]]
    
    [[exitcodes#^EXCOOR|Out of range]]
    
    [[exit-status#^PIPEEX|_Pipe_]] exit status
    
    [[complexfunct#^EXITRETURN1|Specified by a _function return_]]
    
    [[exit-status#^EXITSUCCESS|_Successful_]], **0**
    
    [[exitcodes#^SYSEXITSREF|/usr/include/sysexits.h]], system file listing C/C++ standard exit codes
    

[[internal#^EXPORTREF2|Export]], to make available variables to [[othertypesv#^CHILDREF|child processes]]

- [[internal#^EXPORTAWK|Passing a variable to an embedded _awk_ script]]
    

[[moreadv#^EXPRREF|expr]], _Expression_ evaluator

- [[moreadv#^EXPEXTRSUB|Substring extraction]]
    
- [[manipulating-strings#^SUBSTRINGINDEX2|Substring _index_ (numerical position in string)]]
    
- [[manipulating-strings#^EXPRMATCH|Substring matching]]
    

[[x17129#^EXTREGEX|Extended _Regular Expressions_]]

- **?** (question mark) [[x17129#^QUEXREGEX|Match zero / one characters]]
    
- **( ... )** [[x17129#^PARENGRPS|Group of expressions]]
    
- **\{ N \}** [[x17129#^ESCPCB|"Curly" brackets]], _escaped_, number of character sets to match
    
- **+** [[x17129#^PLUSREF|_Character match_]]
    

* * *

[[mathc#^FACTORREF|factor]], decomposes an integer into its prime factors

- Application: [[mathc#^PRIMES2|Generating prime numbers]]
    

[[internal#^FALSEREF|false]], returns _unsuccessful_ (1) [[exit-status#^EXITSTATUSREF|exit status]]

[[special-characters#^FIELDREF|Field]], a group of characters that comprises an item of data

[[filearchiv|Files / Archiving]]

[[io-redirection#^FDREF|File descriptors]]

- [[io-redirection#^CFD|Closing]]
    
    **n<&-** Close input file descriptor _n_
    
    **0<&-**, **<&-** Close stdin
    
    **n>&-** Close output file descriptor _n_
    
    **1>&-**, **>&-** Close stdout
    
- [[io-redirection#^FDREF1|File handles in _C_]], similarity to
    

[[filearchiv#^OPENSSLREF|File encryption]]

[[moreadv#^FINDREF|find]]

- **{}** [[moreadv#^CURLYBRACKETSREF|Curly brackets]]
    
- **\;** [[moreadv#^FINDREF0|_Escaped_ semicolon]]
    

[[special-characters#^FILTERDEF|Filter]]

- [[special-characters#^FILTERDASH|Using - with file-processing utility as a filter]]
    
- [[assorted-tips#^FILTEROUTP|Feeding output of a filter back to _same_ filter]]
    

[[operators#^NOFLOATINGPOINT|Floating point numbers]], Bash does not recognize

[[textproc#^FOLDREF|fold]], a filter to wrap lines of text

[[internal#^FORKREF|Forking]] a _child_ process

[[loops#^FORLOOPREF1|_for_ loops]]

[[functions#^FUNCTIONREF|Functions]]

- [[complexfunct#^PASSEDARGS|Arguments passed]] referred to by position
    
- [[complexfunct#^CAPTURERETVAL|Capturing the return value]] of a function using [[internal#^ECHOREF|echo]]
    
- [[special-characters#^COLONFNAME|_Colon_]] as function name
    
- [[functions#^FUNCTDEFMUST|Definition must precede]] first call to function
    
- [[complexfunct#^EXITRETURN1|Exit status]]
    
- [[localvar#^LOCALREF1|Local variables]]
    
    and [[localvar#^LOCVARRECUR|recursion]]
    
- [[assorted-tips#^PASSARRAY|Passing an _array_]] to a function
    
- [[complexfunct#^FUNCPOINTERS|Passing pointers]] to a function
    
- [[complexfunct#^PASSEDARGS|Positional parameters]]
    
- [[localvar#^RECURSIONREF0|Recursion]]
    
- [[complexfunct#^REDSTDINFUNC1|Redirecting stdin]] of a function
    
- [[complexfunct#^RETURNREF|return]]
    
    Multiple _return values_ from a function, [[contributed-scripts#^STDDEV|example script]]
    
    [[assorted-tips#^RETARRAY|Returning an _array_]] from a function
    
    [[assorted-tips#^RVT|_Return_ range limits]], workarounds
    
- [[complexfunct#^FSHIFTREF|_Shift_ arguments passed]] to a function
    
- [[functions#^FSTRANGEREF|Unusual function names]]
    

* * *

Games and amusements

- [[assorted-tips#^AGRAM|Anagrams]]
    
- [[commandsub#^AGRAM2|Anagrams]], again
    
- [[contributed-scripts#^BINGO|Bingo Number Generator]]
    
- [[textproc#^CWSOLVER|Crossword puzzle solver]]
    
- [[textproc#^CRYPTOQUOTE|Crypto-Quotes]]
    
- [[bash-ver2#^CARDS|Dealing a deck of cards]]
    
- [[contributed-scripts#^FIFTEEN|Fifteen Puzzle]]
    
- [[colorizing#^HORSERACE|Horse race]]
    
- [[contributed-scripts#^KTOUR|Knight's Tour]]
    
- [[contributed-scripts#^LIFESLOW|"Life" game]]
    
- [[contributed-scripts#^MSQUARE|Magic Squares]]
    
- [[devref1#^MUSICSCR|Music-playing script]]
    
- [[contributed-scripts#^NIM|Nim]]
    
- [[generate-random-integer#^BROWNIAN|Pachinko]]
    
- [[contributed-scripts#^QKY|Perquackey]]
    
- [[contributed-scripts#^PETALS|Petals Around the Rose]]
    
- [[contributed-scripts#^BASHPODDER|Podcasting]]
    
- [[Chapter 27. Arrays#^POEM|Poem]]
    
- [[shell-wrapper#^SPEECH00|Speech generation]]
    
- [[recurnolocvar#^HANOI|Towers of Hanoi]]
    
    [[contributed-scripts#^HANOI2|Graphic version]]
    
    [[contributed-scripts#^HANOI2A|Alternate graphic version]]
    

[[extmisc#^GETOPTY|getopt]], _external_ command for parsing script _command-line_ arguments

- [[manipulating-strings#^GETOPTSIMPLE1|Emulated in a script]]
    

[[internal#^GETOPTSX|getopts]], Bash _builtin_ for parsing script _command-line_ arguments

- [[internal#^GETOPTSOPT|$OPTIND / $OPTARG]]
    

[[subshells#^SCOPEREF|Global]] variable

[[globbingref#^GLOBBINGREF2|Globbing]], filename expansion

- [[globbingref#^HANDLINGFNAMES|Handling filenames correctly]]
    
- [[special-characters#^ASTERISKREF|_Wild cards_]]
    
- [[globbingref#^WDOTFILEWC|Will not match dot files]]
    

[[mathc#^GOLDENRATIO|Golden Ratio]] (_Phi_)

[[other-comparison-operators#^GE0REF|-ge]] , _greater-than or equal_ [[other-comparison-operators#^ICOMPARISON1|integer comparison]] test

[[other-comparison-operators#^GT0REF|-gt]] , _greater-than_ [[other-comparison-operators#^ICOMPARISON1|integer comparison]] test

[[textproc#^GROFFREF|_groff_]], text markup and formatting language

[[contributed-scripts#^GRONSFELD|Gronsfeld cipher]]

[[internal-variables#^GROUPSREF|$GROUPS]], _Groups_ user belongs to

[[filearchiv#^GZIPREF|gzip]], compression utility

* * *

[[internal#^HASHREF|Hashing]], creating lookup keys in a table

- [[contributed-scripts#^HASHEX2_0|_Example script_]]
    

[[textproc#^HEADREF|head]], _echo_ to stdout lines at the beginning of a text file

[[internal#^HELPREF|help]], gives usage summary of a Bash [[internal#^BUILTINREF|builtin]]

[[here-docs#^HEREDOCREF|_Here_ documents]]

- [[here-docs#^ANONHEREDOC0|_Anonymous_ here documents]], using **:**
    
    [[here-docs#^CBLOCK1|Commenting out]] blocks of code
    
    [[here-docs#^HSELFDOC|Self-documenting]] scripts
    
- [[mathc#^BCHEREDOC|_bc_ in a _here document_]]
    
- [[here-docs#^CATSCRIPTREF|_cat_ scripts]]
    
- [[here-docs#^HERECS|Command substitution]]
    
- [[here-docs#^EXSCRIPTREF|_ex_ scripts]]
    
- [[here-docs#^HEREFUNC|_Function_]], supplying input to
    
- [[x17837#^HERESTRINGSREF|_Here_ strings]]
    
    Calculating the [[mathc#^GOLDENRATIO|Golden Ratio]]
    
    [[x17837#^HSPRE|Prepending text]]
    
    [[x17837#^HSLOOP|As the stdin of a _loop_]]
    
    [[x17837#^HSREAD|Using _read_]]
    
- [[here-docs#^LIMITSTRINGREF|_Limit_ string]]
    
    [[here-docs#^EXCLLS|! as a _limit string_]]
    
    [[here-docs#^INDENTEDLS|Closing _limit string_]] may not be indented
    
    [[here-docs#^LIMITSTRDASH|Dash option]] to limit string, <<-LimitString
    
- [[here-docs#^HERELIT|Literal text output]], for generating program code
    
- [[here-docs#^HEREPARAMSUB|Parameter substitution]]
    
    [[here-docs#^HEREESC|Disabling]] _parameter substitution_
    
- [[here-docs#^HEREPASSP|Passing parameters]]
    
- [[here-docs#^HERETEMP|Temporary files]]
    
- [[here-docs#^VIHERE|Using _vi_ non-interactively]]
    

[[histcommands|History commands]]

[[internal-variables#^HOMEDIRREF|$HOME]], _user's home directory_

[[contributed-scripts#^HOMEWORK|Homework assignment solver]]

[[internal-variables#^HOSTNAMEREF|$HOSTNAME]], system _host name_

* * *

[[assorted-tips#^RCSREF|$Id parameter]], in _rcs_ (Revision Control System)

[[tests#^IFTHEN|if [ condition ]; then ...]] _test_ construct

- [[test-constructs#^IFGREPREF|if-grep]], _if_ and [[textproc#^GREPREF|grep]] in combination
    
    [[assorted-tips#^IFGREPFIX|Fixup]] for _if-grep_ test
    

[[internal-variables#^IFSREF|$IFS]], _Internal field separator_ variable

- [[internal-variables#^IFSWS|Defaults to _whitespace_]]
    

[[other-comparison-operators#^ICOMPARISON1|Integer comparison operators]]

[[loops#^DOINREF|in]], _keyword_ preceding [list] in a _for_ loop

[[system#^INITTABREF|Initialization table]], /etc/inittab

[[special-characters#^CODEBLOCKREF|Inline group]], i.e., code block

[[intandnonint#^IITEST|Interactive script]], test for

[[io-redirection#^IOREDIRREF|I/O redirection]]

[[ivr#^IVRREF|Indirect referencing of variables]]

- [[ivr#^IVR2|New notation]], introduced in [[bash-ver2#^BASH2REF|version 2]] of Bash ( [[bash-ver2#^VARREFNEW|example script]])
    

[[system#^IPTABLESREF|iptables]], packet filtering and firewall utility

- [[system#^IPTABLES01|Usage example]]
    
- [[networkprogramming#^IPTABLES02|Example script]]
    

[[loops#^ITERATIONREF|Iteration]]

* * *

[[x9644#^JOBIDTABLE0|Job IDs]], table

[[extmisc#^JOTREF|jot]], Emit a sequence of integers. Equivalent to [[extmisc#^SEQREF|seq]].

- [[extmisc#^JOTRANDOM|Random sequence generation]]
    

[[textproc#^JABH|Just another Bash hacker!]]

* * *

[[internal#^KEYWORDREF|Keywords]]

- [[debugging#^MISSINGKEYWORD|error]], if missing
    

[[x9644#^KILLREF|kill]], terminate a process by [[special-characters#^PROCESSIDDEF|process ID]]

- [[x9644#^ZOMBIEREF|Options]] (-l, -9)
    

[[x9644#^KILLALLREF|killall]], terminate a process _by name_

[[sysscripts#^KILLALL2REF|_killall script_]] in /etc/rc.d/init.d

* * *

[[bash-ver4#^LASTPIPEREF|lastpipe]] shell option

[[other-comparison-operators#^LE0REF|-le]] , _less-than or equal_ [[other-comparison-operators#^ICOMPARISON1|integer comparison]] test

[[internal#^LETREF|let]], setting and carrying out arithmetic operations on variables

- _C-style_ [[internal#^EX46|increment and decrement operators]]
    

[[here-docs#^LIMITSTRINGREF|Limit string]], in a [[here-docs#^HEREDOCREF|here document]]

[[internal-variables#^LINENOREF|$LINENO]], variable indicating the _line number_ where it appears in a script

[[basic-commands#^LINKREF|Link]], file (using _ln_ command)

- [[basic-commands#^LINKMINVOK|Invoking script with multiple names]], using _ln_
    
- [[basic-commands#^SYMLINKREF|_symbolic_ links]], _ln -s_
    

[[list-cons#^LISTCONSREF|List constructs]]

- [[list-cons#^LCONS1|_And_ list]]
    
- [[list-cons#^ORLISTREF|_Or_ list]]
    

[[localvar#^LOCALREF1|Local variables]]

- and [[localvar#^LOCVARRECUR|recursion]]
    

[[localization|Localization]]

[[operators#^LOGOPS1|Logical operators]] (&&, ||, etc.)

[[files#^LOGOUTFILEREF1|Logout file]], the ~/.bash_logout file

[[system#^ISOMOUNTREF0|Loopback device]], mounting a file on a [[devref1#^BLOCKDEVREF|block device]]

[[loops|Loops]]

- [[loop-control#^BRKCONT1|break]] loop control command
    
- [[loop-control#^BRKCONT1|continue]] loop control command
    
- _C_-style loop within [[double-parentheses-construct#^DBLPARENSREF|double parentheses]]
    
    [[loops#^LOOPCSTYLE|_for_ loop]]
    
    [[loops#^WLOOPCSTYLE|_while_ loop]]
    
- [[loops#^DOINREF|do]] (keyword), begins execution of commands within a loop
    
- [[loops#^DOINREF|done]] (keyword), terminates a loop
    
- [[loops#^FORLOOPREF1|_for_ loops]]
    
    _for_ arg _in_ [list]; _do_
    
    [[loops#^LOOPCS|_Command substitution_ to generate [list]]]
    
    [[loops#^LIGLOB|Filename expansion in [list]]]
    
    [[loops#^MULTPARAML|Multiple parameters in each [list] element]]
    
    [[loops#^OMITLIST|Omitting [list]]], defaults to [[internal-variables#^POSPARAMREF|positional parameters]]
    
    [[loops#^PARAMLI|Parameterizing [list]]]
    
    [[loops#^LOOPREDIR|Redirection]]
    
- [[loops#^DOINREF|in]], (keyword) preceding [list] in a _for_ loop
    
- [[nested-loops|Nested loops]]
    
- [[special-characters#^BGLOOP0|Running a loop _in the background_]], _script example_
    
- Semicolon required, when _do_ is on first line of loop
    
    [[loops#^NEEDSEMICOLON|_for_ loop]]
    
    [[loops#^WHILENEEDSEMI|_while_ loop]]
    
- [[loops#^UNTILLOOPREF|until]] loop
    
    _until [ condition-is-true ]; do_
    
- [[loops#^WHILELOOPREF|while]] loop
    
    _while [ condition ]; do_
    
    [[loops#^WHILEFUNC|Function call]] inside test brackets
    
    [[loops#^WHMULTCOND|Multiple conditions]]
    
    [[loops#^WHILENOBRACKETS|Omitting _test brackets_]]
    
    [[loops#^WHREDIR|Redirection]]
    
    [[loops#^WHILEREADREF2|_while read_]] construct
    
- [[loops#^CHOOSELOOP|Which type of loop to use]]
    

Loopback devices

- [[devref1#^LOOPBACKREF|In /dev directory]]
    
- [[system#^ISOMOUNTREF0|Mounting an ISO image]]
    

[[other-comparison-operators#^LT0REF|-lt]] , _less-than_ [[other-comparison-operators#^ICOMPARISON1|integer comparison]] test

* * *

[[extmisc#^M4REF|m4]], macro processing language

[[internal-variables#^MACHTYPEREF|$MACHTYPE]], _Machine type_

[[starting-off-with-a-sha-bang#^MAGNUMREF|Magic number]], marker at the head of a file indicating the file type

[[filearchiv#^MAKEFILEREF|Makefile]], file containing the list of dependencies used by [[filearchiv#^MAKEREF|make]] command

[[basic-commands#^MANREF|man]], _manual page_ (lookup)

- [[contributed-scripts#^MANED|_Man page_ editor]] (script)
    

[[bash-ver4#^MAPFILEREF|mapfile]] builtin, loads an array with a text file

[[mathc|Math commands]]

[[x17129#^METAMEANINGREF|Meta-meaning]]

[[contributed-scripts#^SAMORSE|Morse code training]] script

[[operators#^MODULOREF|Modulo]], arithmetic _remainder_ operator

- Application: [[contributed-scripts#^PRIMES1|Generating prime numbers]]
    

[[mathc#^MONTHLYPMT0|Mortgage calculations]], _example script_

* * *

**-n** [[other-comparison-operators#^STRINGNOTNULL|String not _null_]] test

[[extmisc#^NAMEDPIPEREF|Named pipe]], a temporary FIFO buffer

- [[contributed-scripts#^ZFIFO|_Example script_]]
    

[[system#^NCREF|nc]], _netcat_, a network toolkit for TCP and UDP ports

[[other-comparison-operators#^NEQUALREF|-ne]], _not-equal-to_ [[other-comparison-operators#^ICOMPARISON1|integer comparison]] test

[[special-characters#^NOTREF|Negation operator]], **!**, reverses the sense of a [[tests#^IFTHEN|test]]

[[system#^NETSTATREF|netstat]], Network statistics

[[networkprogramming|Network programming]]

[[textproc#^NLREF|nl]], a filter to number lines of text

[[options#^NOCLOBBERREF|_Noclobber_]], -C option to Bash to prevent overwriting of files

[[operators#^LOGOPS1|_NOT_ logical operator]], **!**

[[othertypesv#^NULLVAR|_null_ variable assignment]], avoiding

* * *

**-o** [[other-comparison-operators#^COMPOUNDOR|Logical OR]] compound comparison test

Obfuscation

- [[special-characters#^COLONFNAME|_Colon_]] as function name
    
- [[contributed-scripts#^HOMEWORK|Homework assignment]]
    
- [[textproc#^JABH|Just another Bash hacker!]]
    

[[escaping#^OCTALREF|octal]], base-8 numbers

[[extmisc#^ODREF|od]], _octal dump_

[[internal-variables#^OLDPWD|$OLDPWD]] Previous working directory

[[filearchiv#^OPENSSLREF|openssl]] encryption utility

Operator

- [[special-characters#^OPERATORDEF|Definition of]]
    
- [[operator-precedence#^OPPRECEDENCE1|Precedence]]
    

[[options#^OPTIONSREF|Options]], passed to shell or script on command line or by [[internal#^SETREF|set]] command

[[list-cons#^ORLISTREF|_Or_ list]]

[[operators#^ORREF|_Or_ logical operator]], **||**

* * *

[[parameter-substitution#^PARAMSUBREF|Parameter substitution]]

- _${parameter+alt_value}_
    
    _${parameter:+alt_value}_
    
    [[parameter-substitution#^PARAMALTV|Alternate value]] of parameter, if set
    
- _${parameter-default}_
    
    _${parameter:-default}_
    
    _${parameter=default}_
    
    _${parameter:=default}_
    
    [[parameter-substitution#^DEFPARAM1|Default parameters]]
    
- _${!varprefix*}_
    
    _${!varprefix@}_
    
    [[parameter-substitution#^VARPREFIXM|Parameter _name_ match]]
    
- _${parameter?err_msg}_
    
    [[parameter-substitution#^QERRMSG|Parameter-unset message]]
    
- _${parameter}_
    
    [[parameter-substitution#^PSSUB1|Value of _parameter_]]
    
- [[bash-ver4#^CASEMODPARAMSUB|_Case modification_]] ([[bash-ver4#^BASH4REF|version 4+]] of Bash).
    
- [[contributed-scripts#^PW0|_Script example_]]
    
- [[refcards#^PARSUBTAB|**Table**]] of _parameter substitution_
    

[[gotchas#^PARCHILDPROBREF|Parent / child process problem]], a _child_ process cannot [[internal#^EXPORTREF|export]] variables to a [[internal#^FORKREF|parent process]]

Parentheses

- [[special-characters#^PARENSREF|Command group]]
    
- [[x17129#^PARENGRPS|Enclose group]] of _Extended Regular Expressions_
    
- [[double-parentheses-construct#^DBLPARENSREF|Double parentheses]], in arithmetic expansion
    

[[internal-variables#^PATHREF|$PATH]], the _path_ (location of system binaries)

- Appending directories to $PATH [[bash-ver3#^PATHAPPEND|using the += operator]].
    

[[special-characters#^PATHNAMEREF|Pathname]], a filename that incorporates the complete _path_ of a given file.

- [[Appendix D. Parsing and Managing Pathnames|Parsing _pathnames_]]
    

[[shell-wrapper#^PERLREF|Perl]], programming language

- [[shell-wrapper#^BASHANDPERL0|Combined]] in the same file with a _Bash_ script
    
- [[shell-wrapper#^PERLEMB|Embedded]] in a _Bash_ script
    

[[contributed-scripts#^QKY|_Perquackey_-type anagramming game]] (_Quackey_ script)

[[contributed-scripts#^PETALS|_Petals Around the Rose_]]

[[special-characters#^PROCESSIDDEF|PID]], _Process ID_, an identification number assigned to a running process.

[[special-characters#^PIPEREF|Pipe]], **|** , a device for passing the output of a command to another command or to the shell

- [[optimizations#^CATABUSE|Avoiding unnecessary commands]] in a _pipe_
    
- [[special-characters#^COMMINPIPE|_Comments_ embedded within]]
    
- [[exit-status#^PIPEEX|Exit status]] of a pipe
    
- [[bash-ver3#^PIPEFAILREF|Pipefail]], _set -o pipefail_ option to indicate [[exit-status#^EXITSTATUSREF|exit status]] within a _pipe_
    
- [[internal-variables#^PIPESTATUSREF|$PIPESTATUS]], _exit status_ of last executed pipe
    
- [[special-characters#^UCREF|Piping output of a command]] to a script
    
- [[basic-commands#^CATLESSEFF|Redirecting stdin]], rather than using [[basic-commands#^CATREF|cat]] in a _pipe_
    

[[gotchas|Pitfalls]]

- [[gotchas#^DASHNREDR|**-** (dash) is _not_ redirection operator]]
    
- [[internal#^DOUBLESLASHREF|**//** (double forward slash)]], behavior of [[internal#^CDREF|cd]] command toward
    
- [[gotchas#^BINSH|#!/bin/sh]] script header disables [[portabilityissues#^BASHCOMPAT|extended _Bash_ features]]
    
- [[optimizations#^CATABUSE|Abuse of _cat_]]
    
- [[gotchas#^CGIREF|_CGI_ programming]], using scripts for
    
- Closing _limit string_ in a _here document_, [[here-docs#^INDENTEDLS|indenting]]
    
- [[gotchas#^DOSNEWLINES|DOS-type newlines (\r\n)]] crash a script
    
- [[quoting-variables#^QUOTINGBSL|_Double-quoting_ the _backslash_ (**\**) character]]
    
- [[internal#^EVALRISK|eval]], risk of using
    
- [[gotchas#^EXECPERM|Execute permission lacking]] for commands within a script
    
- _Exit status_, [[gotchas#^GOTCHAEXITVALANAMALIES|anomalous]]
    
- _Exit status_ [[gotchas#^ARXS1|of arithmetic expression _not_ equivalent to an _error code_]]
    
- [[gotchas#^PARCHILDPROBREF|_Export_ problem]], _child_ process to _parent_ process
    
- [[gotchas#^LATEVERF|Extended _Bash_ features]] not available
    
- [[gotchas#^FAILQUOTE|Failing to _quote_ variables]] within _test_ brackets
    
- [[gotchas#^GNUREF|_GNU_ command set]], in cross-platform scripts
    
- _let_ misuse: [[gotchas#^LETBAD|attempting to set string variables]]
    
- [[gotchas#^RVTCAUTION2|Multiple echo statements]] in a [[assorted-tips#^RVT|function whose output is captured]]
    
- [[othertypesv#^NULLVAR|_null_ variable assignment]]
    
- [[gotchas#^NUMSTRCOMPNE|Numerical and string comparison operators]] _not_ equivalent
    
    [[gotchas#^EQDIF|**=** and **-eq**]] _not_ interchangeable
    
- [[gotchas#^OMITSEMICOLON|Omitting terminal _semicolon_]], in a _curly-bracketed_ [[special-characters#^CODEBLOCKREF|code block]]
    
- Piping
    
    [[gotchas#^PIPELOOP|_echo_ to a loop]]
    
    [[gotchas#^BADREAD0|_echo_ to _read_]] (however, this problem [[Chapter 23. Process Substitution#^GOODREAD0|can be circumvented]])
    
    [[gotchas#^PTAILGREP|_tail_ -f to _grep_]]
    
- Preserving _whitespace_ within a variable, [[quoting-variables#^VARSPLITTING|unintended consequences]]
    
- [[gotchas#^SUIDSCR|_suid_ commands inside a script]]
    
- [[gotchas#^UNDOCF|Undocumented _Bash_ features]], danger of
    
- Updates to _Bash_ [[gotchas#^UPDATEBREAKS|breaking older scripts]]
    
- [[gotchas#^UNINITVAR|Uninitialized variables]]
    
- [[gotchas#^INAPPVN|Variable names]], inappropriate
    
- [[gotchas#^VARSUBSH|Variables in a _subshell_]], _scope_ limited
    
- [[gotchas#^BADREAD0|Subshell in _while-read_ loop]]
    
- [[gotchas#^WSBAD|Whitespace]], misuse of
    

Pointers

- [[io-redirection#^FDREF1|and file descriptors]]
    
- [[complexfunct#^FUNCPOINTERS|and functions]]
    
- [[ivr#^IRRREF|and _indirect references_]]
    
- [[varsubn#^POINTERREF|and _variables_]]
    

[[portabilityissues|Portability issues]] in shell scripting

- [[assorted-tips#^SETPUM|Setting _path_ and _umask_]]
    
- [[portabilityissues#^TESTSUITE0|A _test suite_ script]] (Bash versus classic Bourne shell)
    
- [[assorted-tips#^WHATISREF3|Using _whatis_]]
    

[[othertypesv#^POSPARAMREF1|Positional parameters]]

- [[internal-variables#^APPREF2|$@]], as _separate_ words
    
- [[internal-variables#^APPREF|$*]], as a _single_ word
    
- [[complexfunct#^PASSEDARGS|in functions]]
    

[[starting-off-with-a-sha-bang#^POSIX2REF|POSIX]], _Portable Operating System Interface / UNIX_

- [[portabilityissues#^POSIX3REF|--posix option]]
    
- [[portabilityissues#^POSIX3REF|1003.2 standard]]
    
- [[x17129#^POSIXREF|Character classes]]
    

[[internal-variables#^PPIDREF|$PPID]], _process ID_ of parent process

[[operator-precedence#^OPPRECEDENCE1|Precedence]], operator

[[assorted-tips#^PREPENDREF|_Prepending_]] lines at head of a file, _script example_

Prime numbers

- Generating primes [[mathc#^PRIMES2|using the _factor_ command]]
    
- Generating primes [[contributed-scripts#^PRIMES1|using the _modulo_ operator]]
    
- Sieve of Eratosthenes, [[Chapter 27. Arrays#^PRIMES0|example script]]
    

[[internal#^PRINTFREF|printf]], _formatted print_ command

[[procref1#^PROCREF2|/proc]] directory

- [[procref1#^PROCRUNNING|Running processes]], files describing
    
- [[procref1#^PROCWARNING|Writing to files in /proc]], _warning_
    

[[special-characters#^PROCESSREF|Process]]

- [[othertypesv#^CHILDREF2|Child process]]
    
- [[internal#^PARENTREF|Parent process]]
    
- [[special-characters#^PROCESSIDDEF|Process ID]] (PID)
    

[[Chapter 23. Process Substitution#^PROCESSSUBREF|Process substitution]]

- [[Chapter 23. Process Substitution#^PCC2DIR|To compare contents of directories]]
    
- [[Chapter 23. Process Substitution#^PSFDSTDIN|To supply stdin of a command]]
    
- [[Chapter 23. Process Substitution#^COMMANDSPARENS1|Template]]
    
- [[Chapter 23. Process Substitution#^GOODREAD0|_while-read_ loop without a _subshell_]]
    

[[tabexpansion|Programmable completion]] (tab expansion)

Prompt

- [[internal-variables#^PS1REF|$PS1]], _Main prompt_, seen at command line
    
- [[internal-variables#^SECPROMPTREF|$PS2]], Secondary prompt
    

[[assorted-tips#^PSEUDOCODEREF|Pseudo-code]], as problem-solving method

[[internal-variables#^PWDREF|$PWD]], Current working directory

* * *

[[contributed-scripts#^QKY|Quackey]], a _Perquackey_-type anagramming game (script)

Question mark, **?**

- [[x17129#^QUEXREGEX|Character match]] in an Extended _Regular Expression_
    
- [[special-characters#^QUEXWC|Single-character _wild card_]], in [[globbingref|globbing]]
    
- In a [[special-characters#^CSTRINARY|_C_-style Trinary (ternary) operator]]
    

[[Chapter 5. Quoting#^QUOTINGDEF|Quoting]]

- [[Chapter 5. Quoting#^QUOTINGREF|Character string]]
    
- [[quoting-variables|Variables]]
    
    [[gotchas#^FAILQUOTE|within _test_ brackets]]
    
- [[quoting-variables#^WSQUO|_Whitespace_]], using _quoting_ to preserve
    

* * *

Random numbers

- [[generate-random-integer#^URANDOMREF|/dev/urandom]]
    
- [[generate-random-integer#^AWKRANDOMREF|rand()]], random function in [[C.2. Awk#^AWKREF|awk]]
    
- [[generate-random-integer#^RANDOMVAR01|$RANDOM]], Bash function that returns a pseudorandom integer
    
- [[timedate#^DATERANDREF|Random sequence generation]], using [[timedate#^DATEREF|date]] command
    
- [[extmisc#^JOTRANDOM|Random sequence generation]], using [[extmisc#^JOTREF|jot]]
    
- [[manipulating-strings#^RANDSTRING0|Random string]], generating
    

Raspberry Pi (single-board computer)

- [[extmisc#^RPSDCARD01|Script for preparing a bootable SD card]]
    

[[assorted-tips#^RCSREF|rcs]]

[[internal#^READREF|read]], set value of a variable from [[ioredirintro#^STDINOUTDEF|stdin]]

- [[internal#^READARROW|Detecting _arrow_ keys]]
    
- [[internal#^READOPTIONS|Options]]
    
- [[internal#^READPIPEREF|Piping output of _cat_]] to _read_
    
- [[x17837#^HSREAD|"Prepending" text]]
    
- [[gotchas#^BADREAD0|Problems piping _echo_]] to _read_
    
- [[internal#^READREDIR0|Redirection from a file]] to _read_
    
- [[internal-variables#^REPLYREF|$REPLY]], default _read_ variable
    
- [[internal#^READTIMED|Timed input]]
    
- [[loops#^WHILEREADREF2|_while read_]] construct
    

[[internal#^READLINEREF|readline]] library

[[localvar#^RECURSIONREF|Recursion]]

- [[localvar#^RECURSIONDEMO0|Demonstration of]]
    
- [[localvar#^FACTORIALREF|Factorial]]
    
- [[recurnolocvar#^FIBOREF|Fibonacci sequence]]
    
- [[localvar#^LOCVARRECUR|Local variables]]
    
- [[recursionsct#^SCRIPTRECURSION|Script calling itself recursively]]
    
- [[recurnolocvar#^HANOIREF|Towers of Hanoi]]
    

Redirection

- [[redircb#^REDIRREF|Code blocks]]
    
- [[x17974#^USINGEXECREF|exec <filename]],
    
    to reassign [[io-redirection#^FDREF|file descriptors]]
    
- [[ioredirintro|Introductory-level explanation]] of _I/O redirection_
    
- [[io-redirection#^IOREDIRECTIONREF2|Open a file]] for _both_ reading and writing
    
    <>filename
    
- [[internal#^READREDIR0|_read_ input redirected]] from a file
    
- [[io-redirection#^IOREDIRECTIONREF1|stderr to stdout]]
    
    2>&1
    
- [[special-characters#^COXEX|stdin / stdout]], using **-**
    
- [[complexfunct#^REDSTDINFUNC1|stdinof a _function_]]
    
- [[io-redirection#^IOREDIRECTIONREF|stdout to a file]]
    
    _>_ ... _>>_
    
- [[io-redirection#^IOREDIRECTIONREF1|stdout to _file descriptor_]] _j_
    
    >&j
    
- [[io-redirection#^IOREDIRECTIONREF1|file descriptori to _file descriptor_]] _j_
    
    i>&j
    
- [[special-characters#^REDIROUTERROR2|stdout of a command]] to stderr
    
    >&2
    
- [[special-characters#^REDIROUTERROR|stdout _and_ stderr of a command]] to a file
    
    &>
    
- [[extmisc#^TEEREF|tee]], redirect to a file output of command(s) partway through a [[special-characters#^PIPEREF|pipe]]
    

[[refcards|Reference Cards]]

- [[refcards#^MISCTAB|Miscellaneous constructs]]
    
- [[refcards#^PARSUBTAB|Parameter substitution/expansion]]
    
- [[refcards#^SPECSHVARTAB|Special shell variables]]
    
- [[refcards#^STRINGOPSTAB|String operations]]
    
- Test operators
    
    [[refcards#^BINCOMPTAB|Binary comparison]]
    
    [[refcards#^FILESTAB|Files]]
    

[[regexp#^REGEXREF|_Regular Expressions_]]

- **^** (caret) [[special-characters#^BEGLINEREF|Beginning-of-line]]
    
- **$** (dollar sign) [[x17129#^DOLLARSIGNREF|_Anchor_]]
    
- **.** (dot) [[x17129#^REGEXDOT|Match single character]]
    
- ***** (asterisk) [[special-characters#^ASTERISKREF2|Any number of characters]]
    
- **[[x17129#^BRACKETSREF| ]** (brackets) [Enclose character set to match]]
    
- **\** (backslash) [[x17129#^REGEXBS|Escape]], interpret following character literally
    
- **\< ... \>** (angle brackets, _escaped_) [[x17129#^ANGLEBRAC|Word boundary]]
    
- [[x17129#^EXTREGEX|Extended]] REs
    
    **+** [[x17129#^PLUSREF|_Character match_]]
    
    **\{ \}** [[x17129#^ESCPCB|Escaped "curly" brackets]]
    
    **[[x17129#^POSIXREF|: :]** [POSIX character classes]]
    

[[internal-variables#^REPLYREF|$REPLY]], Default value associated with [[internal#^READREF|read]] command

[[restricted-sh#^RESTRICTEDSHREF|Restricted shell]], shell (or script) with certain commands disabled

[[complexfunct#^RETURNREF|return]], command that terminates a [[functions#^FUNCTIONREF|function]]

[[extmisc#^RUNPARTSREF|run-parts]]

- [[assorted-tips#^RUNPARTSREF2|Running scripts in sequence]], without user intervention
    

* * *

[[subshells#^SCOPEREF|Scope]] of a variable, definition

[[options#^INVOCATIONOPTIONSREF|Script options]], set at command line

[[assorted-tips#^LIBROUTINES|Scripting routines]], library of useful definitions and [[functions#^FUNCTIONREF|functions]]

[[internal-variables#^SECPROMPTREF|Secondary prompt]], **$PS2**

[[securityissues|Security issues]]

- [[system#^NMAPREF|nmap]], _network mapper_ / port scanner
    
- [[system#^SUDOREF|sudo]]
    
- [[gotchas#^SUIDSCR|_suid_ commands inside a script]]
    
- [[securityissues#^INFECTEDSCRIPTS1|Viruses, trojans, and worms]] in scripts
    
- [[securityissues#^SECURITYTIPS1|Writing secure scripts]]
    

[[Appendix C. A Sed and Awk Micro-Primer#^SEDREF|sed]], pattern-based programming language

- [[C.1. Sed#^SEDBASICTABLE|**Table**]], basic operators
    
- [[C.1. Sed#^SEDOPTABLE|**Table**]], examples of operators
    

[[testbranch#^SELECTREF|select]], construct for menu building

- [[testbranch#^INLISTOMIT|**in _list_** omitted]]
    

[[system#^SEMAPHOREREF|Semaphore]]

[[loops#^NEEDSEMICOLON|Semicolon required]], when [[loops#^DOINREF|do]] _keyword_ is on first line of [[loops#^FORLOOPREF1|loop]]

- [[gotchas#^OMITSEMICOLON|When terminating _curly-bracketed_ code block]]
    

[[extmisc#^SEQREF|seq]], Emit a sequence of integers. Equivalent to [[extmisc#^JOTREF|jot]].

[[internal#^SETREF|set]], Change value of internal script variables

- [[debugging#^UNDVARERR|set -u]], Abort script with error message if attempting to use an _undeclared_ variable.
    

[[Part 1. Introduction#^WHATSASCRIPT|Shell script]], definition of

[[shell-wrapper#^SHWRAPPER|Shell wrapper]], script embedding a command or utility

[[othertypesv#^SHIFTREF|shift]], reassigning _positional parameters_

[[internal-variables#^SHLVLREF|$SHLVL]], _shell level_, depth to which the shell (or script) is nested

[[internal#^SHOPTREF|shopt]], change _shell options_

[[debugging#^SIGNALD|Signal]], a message sent to a process

Simulations

- [[generate-random-integer#^BROWNIANREF|Brownian motion]]
    
- [[generate-random-integer#^BROWNIANREF|Galton board]]
    
- [[colorizing#^HORSERACEREF|Horserace]]
    
- [[contributed-scripts#^LIFEREF|_Life_]], game of
    
- [[mathc#^CANNONREF|PI]], approximating by firing cannonballs
    
- [[Chapter 27. Arrays#^STACKEX0|Pushdown _stack_]]
    

[[varsubn#^SNGLQUO|Single quotes]] (**' ... '**) _strong_ [[Chapter 5. Quoting#^QUOTINGREF|quoting]]

[[devref1#^SOCKETREF|Socket]], a communication node associated with an I/O port

Sorting

- [[Chapter 27. Arrays#^BUBBLESORT|Bubble sort]]
    
- [[contributed-scripts#^INSERTIONSORT0|Insertion sort]]
    

[[internal#^SOURCEREF|source]], execute a script or, within a script, import a file

- [[internal#^SOURCEPARAMS|Passing positional parameters]]
    

_Spam_, dealing with

- [[communications#^SPAMLOOKUP_0|_Example script_]]
    
- [[communications#^ISSPAMMER_0|_Example script_]]
    
- [[contributed-scripts#^ISSPAMMER2_0|_Example script_]]
    
- [[contributed-scripts#^WHX0|_Example script_]]
    

[[special-characters#^SCHARLIST1|Special characters]]

Stack

- [[internal-variables#^STACKDEFREF|Definition]]
    
- Emulating a _push-down stack_, [[Chapter 27. Arrays#^STACKEX0|example script]]
    

Standard Deviation, [[contributed-scripts#^STDDEV|example script]]

[[files#^FILESREF1|Startup files]], Bash

[[ioredirintro#^STDINOUTDEF|stdin and stdout]]

[[contributed-scripts#^STOPWATCH|Stopwatch]], example script

Strings

- **=~** [[bash-ver3#^REGEXMATCHREF|String match operator]]
    
- [[other-comparison-operators#^SCOMPARISON1|Comparison]]
    
- [[parameter-substitution#^PSOREX1|Length]]
    
    _${#string}_
    
- [[manipulating-strings#^STRINGMANIP|Manipulation]]
    
- [[manipulating-strings#^AWKSTRINGMANIP2|Manipulation]], using [[C.2. Awk#^AWKREF|awk]]
    
- [[other-comparison-operators#^STRINGNOTNULL|_Null_ string]], testing for
    
- [[contributed-scripts#^PROTECTLITERAL0|Protecting strings]] from expansion and/or reinterpretation, _script example_
    
    [[contributed-scripts#^UNPROTECTLITERAL0|_Unprotecting_ strings]], _script example_
    
- _strchr()_, [[manipulating-strings#^SUBSTRINGINDEX2|equivalent of]]
    
- _strlen()_, [[manipulating-strings#^STRLEN|equivalent of]]
    
- [[filearchiv#^STRINGSREF|strings]] command, find printable strings in a binary or data file
    
- Substring extraction
    
    [[manipulating-strings#^SUBSTREXTR01|${string:position}]]
    
    [[manipulating-strings#^SUBSTREXTR02|${string:position:length}]]
    
    [[moreadv#^EXPEXTRSUB|Using _expr_]]
    
- [[manipulating-strings#^SUBSTRINGINDEX2|Substring _index_]] (numerical position in string)
    
- [[manipulating-strings#^EXPRPAREN|Substring _matching_]], using [[moreadv#^EXPRREF|expr]]
    
- [[parameter-substitution#^PSOREX1|Substring _removal_]]
    
    [[parameter-substitution#^PSOREXSH|${var#Pattern}]]
    
    [[parameter-substitution#^PSOREXLO|${var##Pattern}]]
    
    [[parameter-substitution#^PCTREP1|${var%Pattern}]]
    
    [[parameter-substitution#^PCTREP2|${var%%Pattern}]]
    
- Substring replacement
    
    [[manipulating-strings#^SUBSTRREPL00|${string/substring/replacement}]]
    
    [[manipulating-strings#^SUBSTRREPL01|${string//substring/replacement}]]
    
    [[manipulating-strings#^SUBSTRREPL02|${string/#substring/replacement}]]
    
    [[manipulating-strings#^SUBSTRREPL03|${string/%substring/replacement}]]
    
    [[contributed-scripts#^DAYSBETWEEN0|_Script example_]]
    
- [[refcards#^STRINGOPSTAB|**Table**]] of _string/substring_ manipulation and extraction operators
    

[[varsubn#^SNGLQUO|_Strong_ quoting]] **' ... '**

[[scrstyle|Stylesheet]] for writing scripts

[[subshells#^SUBSHELLSREF|Subshell]]

- [[subshells#^SUBSHELLPARENS1|Command list within parentheses]]
    
- [[subshells#^SUBSHNLEVREF|Variables]], $BASH_SUBSHELL and $SHLVL
    
- Variables in a _subshell_
    
    [[gotchas#^VARSUBSH|_scope_ limited]], but ...
    
    ... [[assorted-tips#^SUBSHTMP|can be accessed outside the subshell?]]
    

[[system#^SUREF|su]] _Substitute user_, log on as a different user or as _root_

[[file-test-operators#^SUIDREF|suid]] (_set user id_) file flag

- [[gotchas#^SUIDSCR|_suid_ commands inside a script]], not advisable
    

[[basic-commands#^SYMLINKREF|Symbolic links]]

[[Chapter 31. Of Zeros and Nulls#^SWAPFILEREF|Swapfiles]]

* * *

[[tabexpansion|Tab completion]]

Table lookup, [[bash-ver2#^RESISTOR|script example]]

[[textproc#^TAILREF|tail]], _echo_ to stdout lines at the (tail) end of a text file

[[filearchiv#^TARREF|tar]], archiving utility

[[extmisc#^TEEREF|tee]], redirect to a file output of command(s) partway through a [[special-characters#^PIPEREF|pipe]]

[[system#^TERMINALSSYS1|Terminals]]

- [[system#^SETSERIALREF|setserial]]
    
- [[system#^SETTERMREF|setterm]]
    
- [[system#^STTYREF|stty]]
    
- [[terminalccmds#^TPUTREF|tput]]
    
- [[system#^WALLREF|wall]]
    

_test_ command

- [[test-constructs#^TTESTREF|Bash _builtin_]]
    
- [[test-constructs#^USRBINTEST|external command]], /usr/bin/test (equivalent to /usr/bin/[)
    

[[test-constructs#^TESTCONSTRUCTS1|Test constructs]]

Test operators

- **-a** [[other-comparison-operators#^COMPOUNDAND|Logical AND]] compound comparison
    
- **-e** [[file-test-operators#^RTIF|File exists]]
    
- **-eq** [[other-comparison-operators#^EQUALREF|is-equal-to]] (integer comparison)
    
- **-f** [[file-test-operators#^REGULARFILE|File is a _regular_ file]]
    
- **-ge** [[other-comparison-operators#^GE0REF|greater-than or equal]] (integer comparison)
    
- **-gt** [[other-comparison-operators#^GT0REF|greater-than]] (integer comparison)
    
- **-le** [[other-comparison-operators#^LE0REF|less-than or equal]] (integer comparison)
    
- **-lt** [[other-comparison-operators#^LT0REF|less-than]] (integer comparison)
    
- **-n** [[other-comparison-operators#^STRINGNOTNULL|not-zero-length]] (string comparison)
    
- **-ne** [[other-comparison-operators#^NEQUALREF|not-equal-to]] (integer comparison)
    
- **-o** [[other-comparison-operators#^COMPOUNDOR|Logical OR]] compound comparison
    
- **-u** [[file-test-operators#^SUIDREF|_suid_ flag set]], file test
    
- **-z** [[other-comparison-operators#^STRINGNULL|is-zero-length]] (string comparison)
    
- **=** [[other-comparison-operators#^SCOMPARISON1|is-equal-to]] (string comparison)
    
    **==** [[other-comparison-operators#^SCOMPARISON2|is-equal-to]] (string comparison)
    
- **<** [[other-comparison-operators#^LTREF|less-than]] (string comparison)
    
- **<** [[other-comparison-operators#^INTLT|less-than]], (integer comparison, within [[double-parentheses-construct|double parentheses]])
    
- **<=** [[other-comparison-operators#^LTEQ|less-than-or-equal]], (integer comparison, within _double parentheses_)
    
- **>** [[other-comparison-operators#^GTREF|greater-than]] (string comparison)
    
- **>** [[other-comparison-operators#^INTGT|greater-than]], (integer comparison, within _double parentheses_)
    
- **>=** [[other-comparison-operators#^GTEQ|greater-than-or-equal]], (integer comparison, within _double parentheses_)
    
- **||** [[operators#^ORREF|Logical OR]]
    
- **&&** [[special-characters#^LOGICALAND|Logical AND]]
    
- **!** [[special-characters#^NOTREF|Negation operator]], inverts [[exit-status#^EXITSTATUSREF|exit status]] of a test
    
    **!=** [[other-comparison-operators#^NOTEQUAL|not-equal-to]] (string comparison)
    
- **Tables** of _test_ operators
    
    [[refcards#^BINCOMPTAB|Binary comparison]]
    
    [[refcards#^FILESTAB|File]]
    

[[textproc|Text and text file processing]]

[[timedate|Time / Date]]

Timed input

- [[internal#^READTIMED|Using _read -t_]]
    
- [[internal-variables#^STTYTO|Using _stty_]]
    
- [[internal-variables#^TIMINGLOOP|Using timing loop]]
    
- [[internal-variables#^TMOUTREF|Using $TMOUT]]
    

[[assorted-tips|Tips and hints]] for Bash scripts

- Array, [[assorted-tips#^RETARRAY|as _return value_ from a function]]
    
    _Associative_ array [[optimizations#^ASSOCARRTST|more efficient]] than a numerically-indexed array
    
- [[complexfunct#^CAPTURERETVAL|Capturing the return value]] of a function, using _echo_
    
- [[networkprogramming#^CGISCRIPT|_CGI_ programming]], using scripts for
    
- Comment blocks
    
    Using [[here-docs#^CBLOCK1|_anonymous here documents_]]
    
    Using [[assorted-tips#^COMOUTBL|_if-then_ constructs]]
    
- [[assorted-tips#^COMMENTH|Comment headers]], special purpose
    
- [[assorted-tips#^CSTYLE|_C_-style syntax]] , for manipulating variables
    
- [[C.1. Sed#^DOUBLESPACE|Double-spacing a text file]]
    
- Filenames prefixed with a dash, [[basic-commands#^DASHREM|removing]]
    
- [[assorted-tips#^FILTEROUTP|Filter]], feeding output back to _same_ filter
    
- Function [[assorted-tips#^RVT|_return_ value workarounds]]
    
- [[assorted-tips#^IFGREPFIX|_if-grep_ test fixup]]
    
- [[assorted-tips#^LIBROUTINES|Library]] of useful definitions and _functions_
    
- [[othertypesv#^NULLVAR|_null_ variable assignment]], avoiding
    
- [[assorted-tips#^PASSARRAY|Passing an _array_]] to a function
    
- $PATH, appending to, [[bash-ver3#^PATHAPPEND|using the += operator]].
    
- [[assorted-tips#^PREPENDREF|_Prepending_]] lines at head of a file
    
- [[assorted-tips#^PROGRESSBAR|Progress bar]] template
    
- [[assorted-tips#^PSEUDOCODEREF|Pseudo-code]]
    
- [[assorted-tips#^RCSREF|rcs]]
    
- [[special-characters#^DEVNULLREDIRECT|Redirecting a _test_ to /dev/null]] to suppress output
    
- [[assorted-tips#^RUNPARTSREF2|Running scripts in sequence]] without user intervention, using [[extmisc#^RUNPARTSREF|run-parts]]
    
- Script [[assorted-tips#^SCRIPTASEMB|as embedded command]]
    
- Script _portability_
    
    [[assorted-tips#^SETPUM|Setting _path_ and _umask_]]
    
    [[assorted-tips#^WHATISREF3|Using _whatis_]]
    
- [[assorted-tips#^SETVAREMB|Setting script variable]] to a block of embedded _sed_ or _awk_ code
    
- Speeding up script execution by [[optimizations#^LCALL|disabling _unicode_]]
    
- Subshell variable, [[assorted-tips#^SUBSHTMP|accessing outside the subshell]]
    
- [[assorted-tips#^INTPARAM|Testing a variable]] to see if it contains only digits
    
- [[special-characters#^DEVNULLREDIRECT|Testing whether a command exists]], using [[internal#^TYPEREF|type]]
    
- [[assorted-tips#^TRACKINGSCR|Tracking script usage]]
    
- [[Chapter 23. Process Substitution#^GOODREAD0|_while-read_ loop without a _subshell_]]
    
- [[assorted-tips#^WIDGETREF|Widgets]], invoking from a script
    

[[internal-variables#^TMOUTREF|$TMOUT]], Timeout interval

[[test-constructs#^TOKENREF|Token]], a symbol that may expand to a [[internal#^KEYWORDREF|keyword]] or command

[[terminalccmds#^TPUTREF|tput]], terminal-control command

[[textproc#^TRREF|tr]], character translation filter

- [[textproc#^TRD2U|DOS to Unix text file conversion]]
    
- [[textproc#^TROPTIONS|Options]]
    
- [[contributed-scripts#^SOUNDEX0|Soundex]], _example script_
    
- [[textproc#^TRVARIANTS|Variants]]
    

[[debugging#^TRAPREF1|_Trap_]], specifying an action upon receipt of a [[debugging#^SIGNALD|signal]]

_Trinary (ternary)_ operator, _C_-style, **var>10?88:99**

- [[special-characters#^CSTRINARY|in _double-parentheses_ construct]]
    
- [[internal#^EX46|in _let_ construct]]
    

[[internal#^TRUEREF|true]], returns _successful_ (0) [[exit-status#^EXITSTATUSREF|exit status]]

[[typing-variables#^DECLARE1REF|typeset]] builtin

- [[typing-variables#^DECLAREOPSREF1|options]]
    

* * *

[[internal-variables#^UIDREF|$UID]], User ID number

[[Chapter 25. Aliases#^UNALIASREF|unalias]], to remove an [[Chapter 25. Aliases#^ALIASREF|alias]]

[[system#^UNAMEREF|uname]], output system information

[[bash-ver4#^UNICODEREF|Unicode]], encoding standard for representing letters and symbols

- [[optimizations#^LCALL|Disabling _unicode_]] to optimize script
    

[[gotchas#^UNINITVAR|Uninitialized variables]]

[[textproc#^UNIQREF|uniq]], filter to remove duplicate lines from a sorted file

[[internal#^UNSETREF|unset]], delete a shell variable

[[loops#^UNTILLOOPREF|until]] loop

_until [ condition-is-true ]; do_

* * *

_Variables_

- [[Chapter 27. Arrays#^ARRAYOPSVARS|Array operations on]]
    
- [[operators#^ASNOP1|Assignment]]
    
    [[varassignment#^EX15_0|_Script example_]]
    
    [[varassignment#^EX16_0|_Script example_]]
    
    [[varsubn#^VARUNSETTING|_Script example_]]
    
- [[internal-variables|_Bash_ internal variables]]
    
- [[assorted-tips#^SETVAREMB|Block of _sed_ or _awk_ code]], setting a variable to
    
- _C-style_ [[double-parentheses-construct#^PLUSPLUSREF|increment/decrement/trinary operations]]
    
- [[internal#^SETREF|Change value of internal script variables]] using _set_
    
- [[typing-variables#^DECLARE1REF|declare]], to modify the properties of variables
    
- [[internal#^UNSETREF|Deleting a shell variable]] using _unset_
    
- [[othertypesv#^ENVREF|Environmental]]
    
- [[parameter-substitution#^EXPREPL1|Expansion / Substring replacement]] operators
    
- [[ivr#^IVRREF|Indirect referencing]]
    
    _eval variable1=\$$variable2_
    
    [[ivr#^IVR2|Newer notation]]
    
    _${!variable}_
    
- [[operators#^INTVARREF|Integer]]
    
- [[untyped#^BVUNTYPED|Integer / string]] (variables are untyped)
    
- [[parameter-substitution#^PSOREX1|Length]]
    
    _${#var}_
    
- [[varsubn#^LVALUEREF|Lvalue]]
    
- [[parameter-substitution#^PSSUB1|Manipulating and expanding]]
    
- [[varsubn#^VARNAMEVAL|_Name_ and _value_ of a variable]], distinguishing between
    
- [[other-comparison-operators#^STRINGNOTNULL|_Null_ string]], testing for
    
- [[othertypesv#^NULLVAR|_Null_ variable assignment]], avoiding
    
- [[quoting-variables|Quoting]]
    
    [[gotchas#^FAILQUOTE|within _test_ brackets]]
    
    [[quoting-variables#^WSQUO|to preserve _whitespace_]]
    
- [[varsubn#^LVALUEREF|rvalue]]
    
- [[varsubn#^VARUNSETTING|Setting to _null_ value]]
    
- [[subshells#^PARVIS|In _subshell_]] not visible to parent shell
    
- Testing a variable [[assorted-tips#^INTPARAM|if it contains only digits]]
    
- [[typing-variables#^TYPINGREF|Typing]], restricting the properties of a variable
    
- [[debugging#^UNDVARERR|Undeclared]], error message
    
- [[varsubn#^UNINITVAR1|Uninitialized]]
    
- [[quoting-variables#^VARSPLITTING|Unquoted variable]], _splitting_
    
- [[internal#^UNSETREF|Unsetting]]
    
- [[untyped#^BVUNTYPED|Untyped]]
    

* * *

[[x9644#^WAITREF|wait]], suspend script execution

- [[x9644#^WAITHANG|To remedy script hang]]
    

[[varsubn#^DBLQUO|_Weak_ quoting]] **" ... "**

[[loops#^WHILELOOPREF|while]] loop

_while [ condition ]; do_

- [[loops#^WHLOOPC|C-style syntax]]
    
- [[loops#^WHILEFUNC|Calling a _function_ within _test_ brackets]]
    
- [[loops#^WHMULTCOND|Multiple conditions]]
    
- [[loops#^WHILENOBRACKETS|Omitting _test_ brackets]]
    
- [[loops#^WHILEREADREF2|_while read_]] construct
    
    [[Chapter 23. Process Substitution#^GOODREAD0|Avoiding a _subshell_]]
    

[[special-characters#^WHITESPACEREF|Whitespace]], spaces, tabs, and newline characters

- [[internal-variables#^IFSWS|$IFS defaults to]]
    
- [[gotchas#^WSBAD|Inappropriate use of]]
    
- [[here-docs#^INDENTEDLS|Preceding closing _limit string_]] in a _here document_, error
    
- [[special-characters#^WSBCOMM|Preceding script comments]]
    
- [[quoting-variables#^WSQUO|_Quoting_]], to preserve _whitespace_ within strings or variables
    
- [[x17129#^WSPOSIX|[:space:]]], _POSIX_ character class
    

[[system#^WHOREF|who]], information about logged on users

- [[system#^WREF|w]]
    
- [[system#^WHOAMIREF|whoami]]
    
- [[system#^LOGNAMEREF|logname]]
    

[[assorted-tips#^WIDGETREF|Widgets]]

[[globbingref#^WILDCARDDEF|Wild card]] characters

- [[special-characters#^ASTERISKREF|Asterisk *]]
    
- In [[loops#^LIGLOB|_[list]_ constructs]]
    
- [[special-characters#^WILDCARDQU|Question mark ?]]
    
- [[globbingref#^WDOTFILEWC|Will not match dot files]]
    

Word splitting

- [[quoting-variables#^WSPLITREF|Definition]]
    
- [[commandsub#^CSWS|Resulting from _command substitution_]]
    

[[shell-wrapper#^SHWRAPPER|Wrapper]], shell

* * *

[[moreadv#^XARGSREF|xargs]], Filter for grouping arguments

- [[moreadv#^XARGSCURLYREF|Curly brackets]]
    
- [[moreadv#^XARGSLIMARGS|Limiting arguments passed]]
    
- [[moreadv#^XARGSLIMARGS|Options]]
    
- Processes arguments [[moreadv#^XARGSONEATATIME|one at a time]]
    
- [[moreadv#^XARGSWS|Whitespace]], handling
    

* * *

[[extmisc#^YESREF|yes]]

- [[extmisc#^YESEMU|Emulation]]
    

* * *

**-z** [[other-comparison-operators#^STRINGNULL|String is _null_]]

[[x9644#^ZOMBIEREF|_Zombie_]], a process that has terminated, but not yet been [[x9644#^KILLREF|killed]] by its [[internal#^PARENTREF|parent]]

|ASCII Table|||