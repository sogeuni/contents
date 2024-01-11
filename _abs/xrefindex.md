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
    
- **\;** [[complex-commands#^FINDREF0|_Escaped_ semicolon]], terminates a [[complex-commands#^FINDREF|find]] command
    
- **;;** [[special-characters#^DOUBLESEMICOLON|Double-semicolon]], terminator in a [[testing-and-branching#^CASEESAC1|case]] option
    
    Required when ...
    
    [[loops#^NEEDSEMICOLON|_do_ keyword is on the first line of _loop_]]
    
    [[gotchas#^OMITSEMICOLON|terminating _curly-bracketed_ code block]]
    
- **;;&** **;&** [[bash-ver4#^NCTERM|Terminators]] in a _case_ option ([[bash-ver4#^BASH4REF|version 4+]] of Bash).
    

**:** Colon

- **:> filename** [[io-redirection#^IOREDIRECTIONREF|Truncate file]] to zero length
    
- [[special-characters#^NULLREF|_null_ command]], equivalent to the [[internal-commands-and-builtins#^TRUEREF|true]] Bash builtin
    
- Used in an [[here-documents#^ANONHEREDOC0|anonymous here document]]
    
- Used in an [[special-characters#^COLONINFUNCTION|otherwise empty function]]
    
- Used as a [[functions#^FSTRANGEREF|function name]]
    

**!** [[special-characters#^NOTREF|Negation operator]], inverts [[exit-status#^NEGCOND|exit status]] of a test or command

- **!=** [[other-comparison-operators#^NOTEQUAL|not-equal-to]] String comparison operator
    

**?** (question mark)

- [[brief-introduction-to-regular-expressions#^QUEXREGEX|Match zero or one characters]], in an [[brief-introduction-to-regular-expressions#^EXTREGEX|Extended Regular Expression]]
    
- [[special-characters#^QUEXWC|Single-character _wild card_]], in [[globbing|globbing]]
    
- In a [[special-characters#^CSTRINARY|_C_-style Trinary operator]]
    

**//** [[internal-commands-and-builtins#^DOUBLESLASHREF|Double forward slash]], behavior of [[internal-commands-and-builtins#^CDREF|cd]] command toward

**.** (dot / period)

- **.** [[special-characters#^DOTREF|Load a file]] (into a script), equivalent to [[internal-commands-and-builtins#^SOURCEREF|source]] command
    
- **.** [[brief-introduction-to-regular-expressions#^REGEXDOT|Match single character]], in a [[regexp#^REGEXREF|Regular Expression]]
    
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
    
- **( ... )** [[brief-introduction-to-regular-expressions#^PARENGRPS|Enclose group]] of _Extended Regular Expressions_
    
- **>( ... )**
    
    **<( ... )** [[process-substitution#^PROCESSSUBREF|Process substitution]]
    
- **... )** [[testing-and-branching#^CASEPAREN|Terminates test-condition]] in _case_ construct
    
- **(( ... ))** [[double-parentheses-construct#^DBLPARENSREF|Double parentheses]], in arithmetic expansion
    

**[[special-characters#^LEFTBRACKET|** [Left bracket]], _test_ construct

**[ ]**Brackets

- [[arrays#^BRACKARRAY|_Array_ element]]
    
- [[brief-introduction-to-regular-expressions#^BRACKETSREF|Enclose character set to match]] in a _Regular Expression_
    
- [[special-characters#^BRACKTEST|_Test_ construct]]
    

**[[test-constructs#^DBLBRACKETS|[ ... ]]** [Double brackets]], extended _test_ construct

**$** [[brief-introduction-to-regular-expressions#^DOLLARSIGNREF|_Anchor_]], in a [[regexp#^REGEXREF|Regular Expression]]

**$** [[varsubn|Prefix to a variable name]]

**$( ... )** [[varassignment#^COMMANDSUBREF0|Command substitution]], setting a variable with output of a command, using parentheses notation

**` ... `** [[command-substitution#^BACKQUOTESREF|Command substitution]], using [[special-characters#^BACKTICKSREF|backquotes]] notation

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
    
    [[indirect-references#^IVR2|Indirect referencing of a variable]], new notation
    
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

- **\< ... \>** [[brief-introduction-to-regular-expressions#^ANGLEBRAC|Angle brackets]], _escaped_, word boundary in a [[regexp#^REGEXREF|Regular Expression]]
    
- **\{ N \}** [[brief-introduction-to-regular-expressions#^ESCPCB|"Curly" brackets]], _escaped_, number of character sets to match in an [[brief-introduction-to-regular-expressions#^EXTREGEX|Extended RE]]
    
- **\;** [[complex-commands#^FINDREF0|_Semicolon_]], _escaped_, terminates a [[complex-commands#^FINDREF|find]] command
    
- **\$$** [[indirect-references#^IVRREF|Indirect reverencing of a variable]], old-style notation
    
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

- [[special-characters#^ASTERISKREF|_Wild card_]], in [[globbing|globbing]]
    
- [[special-characters#^ASTERISKREF2|Any number of characters]] in a [[regexp#^REGEXREF|Regular Expression]]
    
- ****** [[operators#^EXPONENTIATIONREF|Exponentiation]], arithmetic operator
    
- ****** Extended _globbing_ [[bash-ver4#^GLOBSTARREF|file-match operator]]
    

**%** Percent sign

- [[operators#^MODULOREF|Modulo]], division-remainder arithmetic operation
    
- [[parameter-substitution#^PCTPATREF|Substring removal]] (pattern matching) operator
    

**+** Plus sign

- [[brief-introduction-to-regular-expressions#^PLUSREF|_Character match_]], in an [[brief-introduction-to-regular-expressions#^EXTREGEX|extended Regular Expression]]
    
- [[parameter-substitution#^PARAMALTV|Prefix to _alternate parameter_]], in _parameter substitution_
    
- **++** [[double-parentheses-construct#^PLUSPLUSREF|_C-style_ variable increment]], within [[double-parentheses-construct#^DBLPARENSREF|double parentheses]]
    

* * *

_Shell Variables_

**$_** [[internal-variables#^UNDERSCOREREF|Last argument to previous command]]

**$-** [[internal-variables#^FLPREF|Flags passed to script]], using [[internal-commands-and-builtins#^SETREF|set]]

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

Address database, [[testing-and-branching#^EX30|script example]]

_Advanced Bash Scripting Guide_, [[mirrorsites#^WHERE_TARBALL|where to download]]

[[aliases#^ALIASREF|Alias]]

- [[aliases#^UNALIASREF|Removing an _alias_]], using _unalias_
    

[[command-substitution#^AGRAM2|Anagramming]]

[[list-constructs#^LCONS1|_And_ list]]

- [[list-constructs#^ANDDEFAULT|To supply default command-line argument]]
    

[[operators#^LOGOPS1|_And_ logical operator]] **&&**

[[brief-introduction-to-regular-expressions#^ANGLEBRAC|Angle brackets]], _escaped_, **\< . . . \>** word boundary in a [[regexp#^REGEXREF|Regular Expression]]

[[here-documents#^ANONHEREDOC0|Anonymous _here document_]], using **:**

[[file-and-archiving-commands#^FAARCHIVING1|Archiving]]

- [[file-and-archiving-commands#^RPMREF|rpm]]
    
- [[file-and-archiving-commands#^TARREF|tar]]
    

[[arithmetic-expansion#^ARITHEXPREF|Arithmetic expansion]]

- [[test-constructs#^ARXS|_exit status_ of]]
    
- [[arithmetic-expansion#^ARITHEXPVAR1|variations of]]
    

[[operators#^AROPS1|Arithmetic operators]]

- [[operators#^ARITHOPSCOMB|combination operators]], _C_-style
    
    **+=** **-=** ***=** **/=** **%=**
    
    |   |   |
    |---|---|
    |![[../images/note.gif|Note]]|[[bashver3#^PLUSEQSTR|In certain contexts]], **+=** can also function as a _string concatenation_ operator.|
    

[[arrays#^ARRAYREF|Arrays]]

- [[bash-ver4#^ASSOCARR|Associative arrays]]
    
    [[optimizations#^ASSOCARRTST|more efficient]] than conventional arrays
    
- [[arrays#^ARRAYREF|Bracket notation]]
    
- [[arrays#^ARRAYAPPEND0|Concatenating]], _example script_
    
- [[arrays#^COPYARRAY0|Copying]]
    
- [[typing-variables#^ARRAYDECLARE|Declaring]]
    
    declare -a array_name
    
- [[arrays#^ARRAYINDIR|Embedded arrays]]
    
- [[arrays#^EMPTYARRAY0|Empty arrays, empty elements]], _example script_
    
- [[arrays#^ARRAYINDIR|Indirect references]]
    
- [[arrays#^ARRAYINIT0|Initialization]]
    
    array=( element1 element2 ... elementN)
    
    [[arrays#^ARRAYASSIGN0|_Example script_]]
    
    Using [[arrays#^ARRAYINITCS|command substitution]]
    
- [[arrays#^ARRAYINITCS|Loading a file]] into an array
    
- [[arrays#^ARRAYMULTIDIM|Multidimensional]], simulating
    
- [[arrays#^ARRAYNEST|Nesting and embedding]]
    
- [[arrays#^ARRAYNOTATION|Notation and usage]]
    
- [[arrays#^ARRAYNUMELEMENTS|Number of elements in]]
    
    ${#array_name[@]}
    
    ${#array_name[*]}
    
- [[arrays#^ARRAYSYNTAX|Operations]]
    
- [[assorted-tips#^PASSARRAY|Passing an _array_]] to a function
    
- As [[assorted-tips#^RETARRAY|_return value_ from a function]]
    
- Special properties, [[arrays#^ARRAYSPECIALPROPS|example script]]
    
- String operations, [[arrays#^ARRAYSTRINGOPS|example script]]
    
- [[arrays#^ARRAYUNSET|_unset_ deletes array elements]]
    

[[internal-commands-and-builtins#^READARROW|Arrow keys]], detecting

ASCII

- [[special-characters#^ASCIIDEF|Definition]]
    
- [[Appendix T. ASCII Table|Scripts for generating ASCII table]]
    

[[C.2. Awk|C.2. Awk]] field-oriented text processing language

- [[generate-random-integer#^AWKRANDOMREF|rand()]], random function
    
- [[manipulating-strings#^AWKSTRINGMANIP2|String manipulation]]
    
- [[internal-commands-and-builtins#^EXPORTAWK|Using _export_]] to pass a variable to an embedded _awk_ script
    

* * *

Backlight, [[system-and-administrative-commands#^BACKLIGHT|setting the brightness]]

[[special-characters#^BACKTICKSREF|Backquotes]], used in [[command-substitution#^BACKQUOTESREF|command substitution]]

[[math-commands#^BASE0|Base conversion]], _example script_

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

[[time-date-commands#^BATCHPROCREF|Batch processing]]

[[math-commands#^BCREF|bc]], calculator utility

- [[math-commands#^BCHEREDOC|In a _here document_]]
    
- [[math-commands#^BCTEMPLATE|Template]] for calculating a script variable
    

[[bibliography|bibliography]]

[[text-processing-commands#^BISONREF|Bison]] utility

[[operators#^BITWSOPS1|Bitwise operators]]

- [[contributed-scripts#^BASE64|Example script]]
    

[[dev#^BLOCKDEVREF|Block devices]]

- [[file-test-operators#^BLOCKDEVTEST|testing for]]
    

[[special-characters#^CODEBLOCKREF|Blocks of code]]

- [[loops#^NODODONE|Iterating / looping]]
    
- [[special-characters#^BLOCKIO|Redirection]]
    
    _Script example_: [[special-characters#^BLOCKIO2|Redirecting output of a a code block]]
    

[[miscellaneous-commands#^BFS|Bootable flash drives]], creating

[[special-characters#^BRACEEXPREF|Brace expansion]]

- [[special-characters#^BRACEEXPREF33|Extended]], _{a..z}_
    
- [[bash-ver3#^BRACEEXPREF3|Parameterizing]]
    
- With [[bash-ver4#^BRACEEXPREF4|increment and zero-padding]] (new feature in Bash, [[bash-ver4#^BASH4REF|version 4]])
    

Brackets, **[ ]**

- [[arrays#^BRACKARRAY|_Array_ element]]
    
- [[brief-introduction-to-regular-expressions#^BRACKETSREF|Enclose character set to match]] in a _Regular Expression_
    
- [[special-characters#^BRACKTEST|_Test_ construct]]
    

Brackets, _curly_, **{}**, used in

- [[special-characters#^CODEBLOCKREF|Code block]]
    
- [[complex-commands#^CURLYBRACKETSREF|_find_]]
    
- [[brief-introduction-to-regular-expressions#^ESCPCB|_Extended Regular Expressions_]]
    
- [[othertypesv#^BRACKETNOTATION|_Positional parameters_]]
    
- [[complex-commands#^XARGSCURLYREF|_xargs_]]
    

[[loop-control#^BRKCONT1|break]] _loop_ control command

- [[loop-control#^BREAKPARAM|Parameter]] (optional)
    

[[internal-commands-and-builtins#^BUILTINREF|Builtins]] in _Bash_

- [[internal-commands-and-builtins#^BLTINFRK|Do not fork a subprocess]]
    

* * *

[[testing-and-branching#^CASEESAC1|_case_ construct]]

- [[testing-and-branching#^CASECL|Command-line parameters]], handling
    
- [[testing-and-branching#^CSGLOB|Globbing]], filtering strings with
    

[[basic-commands#^CATREF|cat]], con_cat_entate file(s)

- [[optimizations#^CATABUSE|Abuse of]]
    
- [[here-documents#^CATSCRIPTREF|_cat_ scripts]]
    
- [[basic-commands#^CATLESSEFF|Less efficient than redirecting stdin]]
    
- [[internal-commands-and-builtins#^READPIPEREF|Piping the output of]], to a [[internal-commands-and-builtins#^READREF|read]]
    
- [[basic-commands#^CATUSES|Uses of]]
    

[[dev#^CHARDEVREF|Character devices]]

- [[file-test-operators#^CHARDEVTEST|testing for]]
    

[[file-and-archiving-commands#^CHECKSUMREF|Checksum]]

[[othertypesv#^CHILDREF|Child processes]]

[[special-characters#^NULLREF|Colon]], **:** , equivalent to the [[internal-commands-and-builtins#^TRUEREF|true]] Bash builtin

[[colorizing#^COLORIZINGREF|Colorizing scripts]]

- Cycling through the background colors, [[contributed-scripts#^SHOWALLC|example script]]
    
- [[colorizing#^COLORIZTABLE|**Table**]] of color escape sequences
    
- [[colorizing#^COLORIZTEMPL|Template]], colored text on colored background
    

[[operators#^COMMAOP|Comma operator]], linking commands or operations

[[G.2. Bash Command-Line Options|Command-line options]]

[[bash-ver4#^CNFH|command_not_found_handle ()]] _builtin_ error-handling function ([[bash-ver4#^BASH4REF|version 4+]] of Bash)

[[command-substitution#^COMMANDSUBREF|Command substitution]]

- [[command-substitution#^CSPARENS|**$( ... )**]], preferred notation
    
- [[command-substitution#^BACKQUOTESREF|_Backquotes_]]
    
- [[command-substitution#^CSTOOLSET|Extending the _Bash_ toolset]]
    
- [[command-substitution#^CSSUBSH|Invokes a _subshell_]]
    
- [[command-substitution#^CSNEST|Nesting]]
    
- [[command-substitution#^CSTRNL|Removes trailing newlines]]
    
- [[command-substitution#^CSVL|Setting variable from loop output]]
    
- [[command-substitution#^CSWS|Word splitting]]
    

[[assorted-tips#^COMMENTH|Comment headers]], special purpose

Commenting out blocks of code

- Using an [[here-documents#^CBLOCK1|_anonymous_ here document]]
    
- Using an [[assorted-tips#^COMOUTBL|_if-then_ construct]]
    

[[communications-commands|Communications and hosts]]

[[other-comparison-operators#^CCOMPARISON1|Compound comparison]] operators

[[file-and-archiving-commands#^FACOMPRESSION1|Compression utilities]]

- [[file-and-archiving-commands#^BZIPREF|bzip2]]
    
- [[file-and-archiving-commands#^COMPRESSREF|compress]]
    
- [[file-and-archiving-commands#^GZIPREF|gzip]]
    
- [[file-and-archiving-commands#^ZIPREF|zip]]
    

[[loop-control#^BRKCONT1|continue]] loop control command

[[special-characters#^CONTROLCHARREF|Control characters]]

- [[special-characters#^CTLCREF|Control-C]], _break_
    
- [[special-characters#^CTLDREF|Control-D]], terminate / log out / erase
    
- [[special-characters#^CTLGREF|Control-G]], **BEL** (_beep_)
    
- [[special-characters#^CTLHREF|Control-H]], _rubout_
    
- [[special-characters#^CTLJREF|Control-J]], _newline_
    
- [[special-characters#^CTLMREF|Control-M]], carriage return
    

[[bash-ver4#^COPROCREF|Coprocesses]]

[[system-and-administrative-commands#^CRONREF|cron]], scheduling _daemon_

[[assorted-tips#^CSTYLE|_C_-style syntax]] , for handling variables

[[text-processing-commands#^CWSOLVER|Crossword puzzle solver]]

[[contributed-scripts#^GRONSFELD|Cryptography]]

Curly brackets {}

- [[complex-commands#^CURLYBRACKETSREF|in _find_ command]]
    
- [[brief-introduction-to-regular-expressions#^ESCPCB|in an _Extended Regular Expression_]]
    
- [[complex-commands#^XARGSCURLYREF|in _xargs_]]
    

* * *

[[communications-commands#^DAEMONREF|Daemons]], in UNIX-type OS

[[time-date-commands#^DATEREF|date]]

[[math-commands#^DCREF|dc]], calculator utility

[[miscellaneous-commands#^DDREF|dd]], _data duplicator_ command

- [[miscellaneous-commands#^DDCONVERSIONS|Conversions]]
    
- [[miscellaneous-commands#^DDCOPY|Copying raw data]] to/from devices
    
- [[miscellaneous-commands#^DDFDEL|File deletion]], _secure_
    
- [[miscellaneous-commands#^DDKEYSTROKES|Keystrokes]], capturing
    
- [[miscellaneous-commands#^DDOPTIONS|Options]]
    
- [[miscellaneous-commands#^DDRANDOM|Random access]] on a data stream
    
- _Raspberry Pi_, [[miscellaneous-commands#^RPSDCARD01|script for preparing a bootable SD card]]
    
- [[miscellaneous-commands#^DDSWAP|Swapfiles]], initializing
    
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

[[dev-and-proc#^DEVPROCREF|/dev]] directory

- [[Chapter 31. Of Zeros and Nulls#^DEVNULLREF|/dev/null]] pseudo-device file
    
- [[generate-random-integer#^URANDOMREF|/dev/urandom]] pseudo-device file, generating pseudorandom numbers with
    
- [[Chapter 31. Of Zeros and Nulls#^ZEROSREF1|/dev/zero]], pseudo-device file
    

[[dev#^DEVFILEREF|Device file]]

[[assorted-tips#^DIALOGREF|_dialog_]], utility for generating _dialog_ boxes in a script

[[internal-variables#^DIRSTACKREF|$DIRSTACK]] _directory stack_

[[restricted-shells#^DISABLEDCOMMREF|Disabled commands]], in _restricted shells_

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

[[internal-commands-and-builtins#^ECHOREF|echo]]

- [[internal-commands-and-builtins#^ECHOGREPREF|Feeding commands down a _pipe_]]
    
- [[internal-commands-and-builtins#^ECHOCS|Setting a variable]] using [[command-substitution#^COMMANDSUBREF|command substitution]]
    
- [[internal-commands-and-builtins#^BINECHO|/bin/echo]], external _echo_ command
    

[[test-constructs#^ELIFREF1|elif]], Contraction of _else_ and [[tests#^IFTHEN|if]]

[[test-constructs#^ELSEREF|else]]

Encrypting files, using [[file-and-archiving-commands#^OPENSSLREF|openssl]]

[[testing-and-branching#^CASEESAC1|esac]], keyword terminating _case_ construct

[[othertypesv#^ENVREF|_Environmental_ variables]]

[[other-comparison-operators#^EQUALREF|-eq]] , _is-equal-to_ [[other-comparison-operators#^ICOMPARISON1|integer comparison]] test

[[arrays#^PRIMES0|Eratosthenes, Sieve of]], algorithm for generating prime numbers

[[escaping#^SPM|Escaped characters]], special meanings of

- Within [[escaping#^STRQ|$' ... ']] string expansion
    
- [[bash-ver4#^UNICODEREF2|Used with _Unicode_ characters]]
    

[[system-and-administrative-commands#^FSTABREF|/etc/fstab]] (filesystem mount) file

[[files#^DATAFILESREF1|/etc/passwd]] (user account) file

[[internal-variables#^EUIDREF|$EUID]], _Effective user ID_

[[internal-commands-and-builtins#^EVALREF|eval]], Combine and _evaluate_ expression(s), with variable expansion

- [[internal-commands-and-builtins#^EVALEFF|Effects of]], _Example script_
    
- [[internal-commands-and-builtins#^EVALFORCED|Forces _reevaluation_]] of arguments
    
- And [[indirect-references#^EVALINDREF|indirect references]]
    
- [[internal-commands-and-builtins#^EVALRISK|Risk of using]]
    
- [[contributed-scripts#^SAMORSE|Using _eval_ to convert _array_ elements into a command list]]
    
- [[internal-commands-and-builtins#^ARRCHOICE0|Using _eval_ to select among variables]]
    

[[test-constructs#^DBLBRAEV|Evaluation of _octal/hex_ constants within [[ ... ]]]]

[[using-exec#^USINGEXECREF|exec]] command, using in [[io-redirection#^IOREDIRREF|redirection]]

[[exercises|Exercises]]

Exit and Exit status

- [[exit-status#^EXITCOMMANDREF|exit]] command
    
- [[exit-status#^EXITSTATUSREF|Exit status]] (_exit code_, _return_ status of a command)
    
    [[exitcodes#^EXITCODESREF|**Table**]], _Exit codes_ with special meanings
    
    [[gotchas#^GOTCHAEXITVALANAMALIES|Anomalous]]
    
    [[exitcodes#^EXCOOR|Out of range]]
    
    [[exit-status#^PIPEEX|_Pipe_]] exit status
    
    [[complex-functions-and-function-complexities#^EXITRETURN1|Specified by a _function return_]]
    
    [[exit-status#^EXITSUCCESS|_Successful_]], **0**
    
    [[exitcodes#^SYSEXITSREF|/usr/include/sysexits.h]], system file listing C/C++ standard exit codes
    

[[internal-commands-and-builtins#^EXPORTREF2|Export]], to make available variables to [[othertypesv#^CHILDREF|child processes]]

- [[internal-commands-and-builtins#^EXPORTAWK|Passing a variable to an embedded _awk_ script]]
    

[[complex-commands#^EXPRREF|expr]], _Expression_ evaluator

- [[complex-commands#^EXPEXTRSUB|Substring extraction]]
    
- [[manipulating-strings#^SUBSTRINGINDEX2|Substring _index_ (numerical position in string)]]
    
- [[manipulating-strings#^EXPRMATCH|Substring matching]]
    

[[brief-introduction-to-regular-expressions#^EXTREGEX|Extended _Regular Expressions_]]

- **?** (question mark) [[brief-introduction-to-regular-expressions#^QUEXREGEX|Match zero / one characters]]
    
- **( ... )** [[brief-introduction-to-regular-expressions#^PARENGRPS|Group of expressions]]
    
- **\{ N \}** [[brief-introduction-to-regular-expressions#^ESCPCB|"Curly" brackets]], _escaped_, number of character sets to match
    
- **+** [[brief-introduction-to-regular-expressions#^PLUSREF|_Character match_]]
    

* * *

[[math-commands#^FACTORREF|factor]], decomposes an integer into its prime factors

- Application: [[math-commands#^PRIMES2|Generating prime numbers]]
    

[[internal-commands-and-builtins#^FALSEREF|false]], returns _unsuccessful_ (1) [[exit-status#^EXITSTATUSREF|exit status]]

[[special-characters#^FIELDREF|Field]], a group of characters that comprises an item of data

[[file-and-archiving-commands|Files / Archiving]]

[[io-redirection#^FDREF|File descriptors]]

- [[io-redirection#^CFD|Closing]]
    
    **n<&-** Close input file descriptor _n_
    
    **0<&-**, **<&-** Close stdin
    
    **n>&-** Close output file descriptor _n_
    
    **1>&-**, **>&-** Close stdout
    
- [[io-redirection#^FDREF1|File handles in _C_]], similarity to
    

[[file-and-archiving-commands#^OPENSSLREF|File encryption]]

[[complex-commands#^FINDREF|find]]

- **{}** [[complex-commands#^CURLYBRACKETSREF|Curly brackets]]
    
- **\;** [[complex-commands#^FINDREF0|_Escaped_ semicolon]]
    

[[special-characters#^FILTERDEF|Filter]]

- [[special-characters#^FILTERDASH|Using - with file-processing utility as a filter]]
    
- [[assorted-tips#^FILTEROUTP|Feeding output of a filter back to _same_ filter]]
    

[[operators#^NOFLOATINGPOINT|Floating point numbers]], Bash does not recognize

[[text-processing-commands#^FOLDREF|fold]], a filter to wrap lines of text

[[internal-commands-and-builtins#^FORKREF|Forking]] a _child_ process

[[loops#^FORLOOPREF1|_for_ loops]]

[[functions#^FUNCTIONREF|Functions]]

- [[complex-functions-and-function-complexities#^PASSEDARGS|Arguments passed]] referred to by position
    
- [[complex-functions-and-function-complexities#^CAPTURERETVAL|Capturing the return value]] of a function using [[internal-commands-and-builtins#^ECHOREF|echo]]
    
- [[special-characters#^COLONFNAME|_Colon_]] as function name
    
- [[functions#^FUNCTDEFMUST|Definition must precede]] first call to function
    
- [[complex-functions-and-function-complexities#^EXITRETURN1|Exit status]]
    
- [[local-variables#^LOCALREF1|Local variables]]
    
    and [[local-variables#^LOCVARRECUR|recursion]]
    
- [[assorted-tips#^PASSARRAY|Passing an _array_]] to a function
    
- [[complex-functions-and-function-complexities#^FUNCPOINTERS|Passing pointers]] to a function
    
- [[complex-functions-and-function-complexities#^PASSEDARGS|Positional parameters]]
    
- [[local-variables#^RECURSIONREF0|Recursion]]
    
- [[complex-functions-and-function-complexities#^REDSTDINFUNC1|Redirecting stdin]] of a function
    
- [[complex-functions-and-function-complexities#^RETURNREF|return]]
    
    Multiple _return values_ from a function, [[contributed-scripts#^STDDEV|example script]]
    
    [[assorted-tips#^RETARRAY|Returning an _array_]] from a function
    
    [[assorted-tips#^RVT|_Return_ range limits]], workarounds
    
- [[complex-functions-and-function-complexities#^FSHIFTREF|_Shift_ arguments passed]] to a function
    
- [[functions#^FSTRANGEREF|Unusual function names]]
    

* * *

Games and amusements

- [[assorted-tips#^AGRAM|Anagrams]]
    
- [[command-substitution#^AGRAM2|Anagrams]], again
    
- [[contributed-scripts#^BINGO|Bingo Number Generator]]
    
- [[text-processing-commands#^CWSOLVER|Crossword puzzle solver]]
    
- [[text-processing-commands#^CRYPTOQUOTE|Crypto-Quotes]]
    
- [[bash-ver2#^CARDS|Dealing a deck of cards]]
    
- [[contributed-scripts#^FIFTEEN|Fifteen Puzzle]]
    
- [[colorizing#^HORSERACE|Horse race]]
    
- [[contributed-scripts#^KTOUR|Knight's Tour]]
    
- [[contributed-scripts#^LIFESLOW|"Life" game]]
    
- [[contributed-scripts#^MSQUARE|Magic Squares]]
    
- [[dev#^MUSICSCR|Music-playing script]]
    
- [[contributed-scripts#^NIM|Nim]]
    
- [[generate-random-integer#^BROWNIAN|Pachinko]]
    
- [[contributed-scripts#^QKY|Perquackey]]
    
- [[contributed-scripts#^PETALS|Petals Around the Rose]]
    
- [[contributed-scripts#^BASHPODDER|Podcasting]]
    
- [[arrays#^POEM|Poem]]
    
- [[shell-wrapper#^SPEECH00|Speech generation]]
    
- [[recursion-without-local-variables#^HANOI|Towers of Hanoi]]
    
    [[contributed-scripts#^HANOI2|Graphic version]]
    
    [[contributed-scripts#^HANOI2A|Alternate graphic version]]
    

[[miscellaneous-commands#^GETOPTY|getopt]], _external_ command for parsing script _command-line_ arguments

- [[manipulating-strings#^GETOPTSIMPLE1|Emulated in a script]]
    

[[internal-commands-and-builtins#^GETOPTSX|getopts]], Bash _builtin_ for parsing script _command-line_ arguments

- [[internal-commands-and-builtins#^GETOPTSOPT|$OPTIND / $OPTARG]]
    

[[subshells#^SCOPEREF|Global]] variable

[[globbing#^GLOBBINGREF2|Globbing]], filename expansion

- [[globbing#^HANDLINGFNAMES|Handling filenames correctly]]
    
- [[special-characters#^ASTERISKREF|_Wild cards_]]
    
- [[globbing#^WDOTFILEWC|Will not match dot files]]
    

[[math-commands#^GOLDENRATIO|Golden Ratio]] (_Phi_)

[[other-comparison-operators#^GE0REF|-ge]] , _greater-than or equal_ [[other-comparison-operators#^ICOMPARISON1|integer comparison]] test

[[other-comparison-operators#^GT0REF|-gt]] , _greater-than_ [[other-comparison-operators#^ICOMPARISON1|integer comparison]] test

[[text-processing-commands#^GROFFREF|_groff_]], text markup and formatting language

[[contributed-scripts#^GRONSFELD|Gronsfeld cipher]]

[[internal-variables#^GROUPSREF|$GROUPS]], _Groups_ user belongs to

[[file-and-archiving-commands#^GZIPREF|gzip]], compression utility

* * *

[[internal-commands-and-builtins#^HASHREF|Hashing]], creating lookup keys in a table

- [[contributed-scripts#^HASHEX2_0|_Example script_]]
    

[[text-processing-commands#^HEADREF|head]], _echo_ to stdout lines at the beginning of a text file

[[internal-commands-and-builtins#^HELPREF|help]], gives usage summary of a Bash [[internal-commands-and-builtins#^BUILTINREF|builtin]]

[[here-documents#^HEREDOCREF|_Here_ documents]]

- [[here-documents#^ANONHEREDOC0|_Anonymous_ here documents]], using **:**
    
    [[here-documents#^CBLOCK1|Commenting out]] blocks of code
    
    [[here-documents#^HSELFDOC|Self-documenting]] scripts
    
- [[math-commands#^BCHEREDOC|_bc_ in a _here document_]]
    
- [[here-documents#^CATSCRIPTREF|_cat_ scripts]]
    
- [[here-documents#^HERECS|Command substitution]]
    
- [[here-documents#^EXSCRIPTREF|_ex_ scripts]]
    
- [[here-documents#^HEREFUNC|_Function_]], supplying input to
    
- [[here-strings#^HERESTRINGSREF|_Here_ strings]]
    
    Calculating the [[math-commands#^GOLDENRATIO|Golden Ratio]]
    
    [[here-strings#^HSPRE|Prepending text]]
    
    [[here-strings#^HSLOOP|As the stdin of a _loop_]]
    
    [[here-strings#^HSREAD|Using _read_]]
    
- [[here-documents#^LIMITSTRINGREF|_Limit_ string]]
    
    [[here-documents#^EXCLLS|! as a _limit string_]]
    
    [[here-documents#^INDENTEDLS|Closing _limit string_]] may not be indented
    
    [[here-documents#^LIMITSTRDASH|Dash option]] to limit string, <<-LimitString
    
- [[here-documents#^HERELIT|Literal text output]], for generating program code
    
- [[here-documents#^HEREPARAMSUB|Parameter substitution]]
    
    [[here-documents#^HEREESC|Disabling]] _parameter substitution_
    
- [[here-documents#^HEREPASSP|Passing parameters]]
    
- [[here-documents#^HERETEMP|Temporary files]]
    
- [[here-documents#^VIHERE|Using _vi_ non-interactively]]
    

[[histcommands|History commands]]

[[internal-variables#^HOMEDIRREF|$HOME]], _user's home directory_

[[contributed-scripts#^HOMEWORK|Homework assignment solver]]

[[internal-variables#^HOSTNAMEREF|$HOSTNAME]], system _host name_

* * *

[[assorted-tips#^RCSREF|$Id parameter]], in _rcs_ (Revision Control System)

[[tests#^IFTHEN|if [ condition ]; then ...]] _test_ construct

- [[test-constructs#^IFGREPREF|if-grep]], _if_ and [[text-processing-commands#^GREPREF|grep]] in combination
    
    [[assorted-tips#^IFGREPFIX|Fixup]] for _if-grep_ test
    

[[internal-variables#^IFSREF|$IFS]], _Internal field separator_ variable

- [[internal-variables#^IFSWS|Defaults to _whitespace_]]
    

[[other-comparison-operators#^ICOMPARISON1|Integer comparison operators]]

[[loops#^DOINREF|in]], _keyword_ preceding [list] in a _for_ loop

[[system-and-administrative-commands#^INITTABREF|Initialization table]], /etc/inittab

[[special-characters#^CODEBLOCKREF|Inline group]], i.e., code block

[[intandnonint#^IITEST|Interactive script]], test for

[[io-redirection#^IOREDIRREF|I/O redirection]]

[[indirect-references#^IVRREF|Indirect referencing of variables]]

- [[indirect-references#^IVR2|New notation]], introduced in [[bash-ver2#^BASH2REF|version 2]] of Bash ( [[bash-ver2#^VARREFNEW|example script]])
    

[[system-and-administrative-commands#^IPTABLESREF|iptables]], packet filtering and firewall utility

- [[system-and-administrative-commands#^IPTABLES01|Usage example]]
    
- [[networkprogramming#^IPTABLES02|Example script]]
    

[[loops#^ITERATIONREF|Iteration]]

* * *

[[job-control-commands#^JOBIDTABLE0|Job IDs]], table

[[miscellaneous-commands#^JOTREF|jot]], Emit a sequence of integers. Equivalent to [[miscellaneous-commands#^SEQREF|seq]].

- [[miscellaneous-commands#^JOTRANDOM|Random sequence generation]]
    

[[text-processing-commands#^JABH|Just another Bash hacker!]]

* * *

[[internal-commands-and-builtins#^KEYWORDREF|Keywords]]

- [[debugging#^MISSINGKEYWORD|error]], if missing
    

[[job-control-commands#^KILLREF|kill]], terminate a process by [[special-characters#^PROCESSIDDEF|process ID]]

- [[job-control-commands#^ZOMBIEREF|Options]] (-l, -9)
    

[[job-control-commands#^KILLALLREF|killall]], terminate a process _by name_

[[analyzing-a-system-script#^KILLALL2REF|_killall script_]] in /etc/rc.d/init.d

* * *

[[bash-ver4#^LASTPIPEREF|lastpipe]] shell option

[[other-comparison-operators#^LE0REF|-le]] , _less-than or equal_ [[other-comparison-operators#^ICOMPARISON1|integer comparison]] test

[[internal-commands-and-builtins#^LETREF|let]], setting and carrying out arithmetic operations on variables

- _C-style_ [[internal-commands-and-builtins#^EX46|increment and decrement operators]]
    

[[here-documents#^LIMITSTRINGREF|Limit string]], in a [[here-documents#^HEREDOCREF|here document]]

[[internal-variables#^LINENOREF|$LINENO]], variable indicating the _line number_ where it appears in a script

[[basic-commands#^LINKREF|Link]], file (using _ln_ command)

- [[basic-commands#^LINKMINVOK|Invoking script with multiple names]], using _ln_
    
- [[basic-commands#^SYMLINKREF|_symbolic_ links]], _ln -s_
    

[[list-constructs#^LISTCONSREF|List constructs]]

- [[list-constructs#^LCONS1|_And_ list]]
    
- [[list-constructs#^ORLISTREF|_Or_ list]]
    

[[local-variables#^LOCALREF1|Local variables]]

- and [[local-variables#^LOCVARRECUR|recursion]]
    

[[localization|Localization]]

[[operators#^LOGOPS1|Logical operators]] (&&, ||, etc.)

[[files#^LOGOUTFILEREF1|Logout file]], the ~/.bash_logout file

[[system-and-administrative-commands#^ISOMOUNTREF0|Loopback device]], mounting a file on a [[dev#^BLOCKDEVREF|block device]]

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

- [[dev#^LOOPBACKREF|In /dev directory]]
    
- [[system-and-administrative-commands#^ISOMOUNTREF0|Mounting an ISO image]]
    

[[other-comparison-operators#^LT0REF|-lt]] , _less-than_ [[other-comparison-operators#^ICOMPARISON1|integer comparison]] test

* * *

[[miscellaneous-commands#^M4REF|m4]], macro processing language

[[internal-variables#^MACHTYPEREF|$MACHTYPE]], _Machine type_

[[starting-off-with-a-sha-bang#^MAGNUMREF|Magic number]], marker at the head of a file indicating the file type

[[file-and-archiving-commands#^MAKEFILEREF|Makefile]], file containing the list of dependencies used by [[file-and-archiving-commands#^MAKEREF|make]] command

[[basic-commands#^MANREF|man]], _manual page_ (lookup)

- [[contributed-scripts#^MANED|_Man page_ editor]] (script)
    

[[bash-ver4#^MAPFILEREF|mapfile]] builtin, loads an array with a text file

[[math-commands|Math commands]]

[[brief-introduction-to-regular-expressions#^METAMEANINGREF|Meta-meaning]]

[[contributed-scripts#^SAMORSE|Morse code training]] script

[[operators#^MODULOREF|Modulo]], arithmetic _remainder_ operator

- Application: [[contributed-scripts#^PRIMES1|Generating prime numbers]]
    

[[math-commands#^MONTHLYPMT0|Mortgage calculations]], _example script_

* * *

**-n** [[other-comparison-operators#^STRINGNOTNULL|String not _null_]] test

[[miscellaneous-commands#^NAMEDPIPEREF|Named pipe]], a temporary FIFO buffer

- [[contributed-scripts#^ZFIFO|_Example script_]]
    

[[system-and-administrative-commands#^NCREF|nc]], _netcat_, a network toolkit for TCP and UDP ports

[[other-comparison-operators#^NEQUALREF|-ne]], _not-equal-to_ [[other-comparison-operators#^ICOMPARISON1|integer comparison]] test

[[special-characters#^NOTREF|Negation operator]], **!**, reverses the sense of a [[tests#^IFTHEN|test]]

[[system-and-administrative-commands#^NETSTATREF|netstat]], Network statistics

[[networkprogramming|Network programming]]

[[text-processing-commands#^NLREF|nl]], a filter to number lines of text

[[options#^NOCLOBBERREF|_Noclobber_]], -C option to Bash to prevent overwriting of files

[[operators#^LOGOPS1|_NOT_ logical operator]], **!**

[[othertypesv#^NULLVAR|_null_ variable assignment]], avoiding

* * *

**-o** [[other-comparison-operators#^COMPOUNDOR|Logical OR]] compound comparison test

Obfuscation

- [[special-characters#^COLONFNAME|_Colon_]] as function name
    
- [[contributed-scripts#^HOMEWORK|Homework assignment]]
    
- [[text-processing-commands#^JABH|Just another Bash hacker!]]
    

[[escaping#^OCTALREF|octal]], base-8 numbers

[[miscellaneous-commands#^ODREF|od]], _octal dump_

[[internal-variables#^OLDPWD|$OLDPWD]] Previous working directory

[[file-and-archiving-commands#^OPENSSLREF|openssl]] encryption utility

Operator

- [[special-characters#^OPERATORDEF|Definition of]]
    
- [[operator-precedence#^OPPRECEDENCE1|Precedence]]
    

[[options#^OPTIONSREF|Options]], passed to shell or script on command line or by [[internal-commands-and-builtins#^SETREF|set]] command

[[list-constructs#^ORLISTREF|_Or_ list]]

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
    

[[gotchas#^PARCHILDPROBREF|Parent / child process problem]], a _child_ process cannot [[internal-commands-and-builtins#^EXPORTREF|export]] variables to a [[internal-commands-and-builtins#^FORKREF|parent process]]

Parentheses

- [[special-characters#^PARENSREF|Command group]]
    
- [[brief-introduction-to-regular-expressions#^PARENGRPS|Enclose group]] of _Extended Regular Expressions_
    
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
    
- [[internal-commands-and-builtins#^DOUBLESLASHREF|**//** (double forward slash)]], behavior of [[internal-commands-and-builtins#^CDREF|cd]] command toward
    
- [[gotchas#^BINSH|#!/bin/sh]] script header disables [[portabilityissues#^BASHCOMPAT|extended _Bash_ features]]
    
- [[optimizations#^CATABUSE|Abuse of _cat_]]
    
- [[gotchas#^CGIREF|_CGI_ programming]], using scripts for
    
- Closing _limit string_ in a _here document_, [[here-documents#^INDENTEDLS|indenting]]
    
- [[gotchas#^DOSNEWLINES|DOS-type newlines (\r\n)]] crash a script
    
- [[quoting-variables#^QUOTINGBSL|_Double-quoting_ the _backslash_ (**\**) character]]
    
- [[internal-commands-and-builtins#^EVALRISK|eval]], risk of using
    
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
    
    [[gotchas#^BADREAD0|_echo_ to _read_]] (however, this problem [[process-substitution#^GOODREAD0|can be circumvented]])
    
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
    
- [[complex-functions-and-function-complexities#^FUNCPOINTERS|and functions]]
    
- [[indirect-references#^IRRREF|and _indirect references_]]
    
- [[varsubn#^POINTERREF|and _variables_]]
    

[[portabilityissues|Portability issues]] in shell scripting

- [[assorted-tips#^SETPUM|Setting _path_ and _umask_]]
    
- [[portabilityissues#^TESTSUITE0|A _test suite_ script]] (Bash versus classic Bourne shell)
    
- [[assorted-tips#^WHATISREF3|Using _whatis_]]
    

[[othertypesv#^POSPARAMREF1|Positional parameters]]

- [[internal-variables#^APPREF2|$@]], as _separate_ words
    
- [[internal-variables#^APPREF|$*]], as a _single_ word
    
- [[complex-functions-and-function-complexities#^PASSEDARGS|in functions]]
    

[[starting-off-with-a-sha-bang#^POSIX2REF|POSIX]], _Portable Operating System Interface / UNIX_

- [[portabilityissues#^POSIX3REF|--posix option]]
    
- [[portabilityissues#^POSIX3REF|1003.2 standard]]
    
- [[brief-introduction-to-regular-expressions#^POSIXREF|Character classes]]
    

[[internal-variables#^PPIDREF|$PPID]], _process ID_ of parent process

[[operator-precedence#^OPPRECEDENCE1|Precedence]], operator

[[assorted-tips#^PREPENDREF|_Prepending_]] lines at head of a file, _script example_

Prime numbers

- Generating primes [[math-commands#^PRIMES2|using the _factor_ command]]
    
- Generating primes [[contributed-scripts#^PRIMES1|using the _modulo_ operator]]
    
- Sieve of Eratosthenes, [[arrays#^PRIMES0|example script]]
    

[[internal-commands-and-builtins#^PRINTFREF|printf]], _formatted print_ command

[[proc#^PROCREF2|/proc]] directory

- [[proc#^PROCRUNNING|Running processes]], files describing
    
- [[proc#^PROCWARNING|Writing to files in /proc]], _warning_
    

[[special-characters#^PROCESSREF|Process]]

- [[othertypesv#^CHILDREF2|Child process]]
    
- [[internal-commands-and-builtins#^PARENTREF|Parent process]]
    
- [[special-characters#^PROCESSIDDEF|Process ID]] (PID)
    

[[process-substitution#^PROCESSSUBREF|Process substitution]]

- [[process-substitution#^PCC2DIR|To compare contents of directories]]
    
- [[process-substitution#^PSFDSTDIN|To supply stdin of a command]]
    
- [[process-substitution#^COMMANDSPARENS1|Template]]
    
- [[process-substitution#^GOODREAD0|_while-read_ loop without a _subshell_]]
    

[[tabexpansion|Programmable completion]] (tab expansion)

Prompt

- [[internal-variables#^PS1REF|$PS1]], _Main prompt_, seen at command line
    
- [[internal-variables#^SECPROMPTREF|$PS2]], Secondary prompt
    

[[assorted-tips#^PSEUDOCODEREF|Pseudo-code]], as problem-solving method

[[internal-variables#^PWDREF|$PWD]], Current working directory

* * *

[[contributed-scripts#^QKY|Quackey]], a _Perquackey_-type anagramming game (script)

Question mark, **?**

- [[brief-introduction-to-regular-expressions#^QUEXREGEX|Character match]] in an Extended _Regular Expression_
    
- [[special-characters#^QUEXWC|Single-character _wild card_]], in [[globbing|globbing]]
    
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
    
- [[time-date-commands#^DATERANDREF|Random sequence generation]], using [[time-date-commands#^DATEREF|date]] command
    
- [[miscellaneous-commands#^JOTRANDOM|Random sequence generation]], using [[miscellaneous-commands#^JOTREF|jot]]
    
- [[manipulating-strings#^RANDSTRING0|Random string]], generating
    

Raspberry Pi (single-board computer)

- [[miscellaneous-commands#^RPSDCARD01|Script for preparing a bootable SD card]]
    

[[assorted-tips#^RCSREF|rcs]]

[[internal-commands-and-builtins#^READREF|read]], set value of a variable from [[ioredirintro#^STDINOUTDEF|stdin]]

- [[internal-commands-and-builtins#^READARROW|Detecting _arrow_ keys]]
    
- [[internal-commands-and-builtins#^READOPTIONS|Options]]
    
- [[internal-commands-and-builtins#^READPIPEREF|Piping output of _cat_]] to _read_
    
- [[here-strings#^HSREAD|"Prepending" text]]
    
- [[gotchas#^BADREAD0|Problems piping _echo_]] to _read_
    
- [[internal-commands-and-builtins#^READREDIR0|Redirection from a file]] to _read_
    
- [[internal-variables#^REPLYREF|$REPLY]], default _read_ variable
    
- [[internal-commands-and-builtins#^READTIMED|Timed input]]
    
- [[loops#^WHILEREADREF2|_while read_]] construct
    

[[internal-commands-and-builtins#^READLINEREF|readline]] library

[[local-variables#^RECURSIONREF|Recursion]]

- [[local-variables#^RECURSIONDEMO0|Demonstration of]]
    
- [[local-variables#^FACTORIALREF|Factorial]]
    
- [[recursion-without-local-variables#^FIBOREF|Fibonacci sequence]]
    
- [[local-variables#^LOCVARRECUR|Local variables]]
    
- [[recursionsct#^SCRIPTRECURSION|Script calling itself recursively]]
    
- [[recursion-without-local-variables#^HANOIREF|Towers of Hanoi]]
    

Redirection

- [[redirecting-code-blocks#^REDIRREF|Code blocks]]
    
- [[using-exec#^USINGEXECREF|exec <filename]],
    
    to reassign [[io-redirection#^FDREF|file descriptors]]
    
- [[ioredirintro|Introductory-level explanation]] of _I/O redirection_
    
- [[io-redirection#^IOREDIRECTIONREF2|Open a file]] for _both_ reading and writing
    
    <>filename
    
- [[internal-commands-and-builtins#^READREDIR0|_read_ input redirected]] from a file
    
- [[io-redirection#^IOREDIRECTIONREF1|stderr to stdout]]
    
    2>&1
    
- [[special-characters#^COXEX|stdin / stdout]], using **-**
    
- [[complex-functions-and-function-complexities#^REDSTDINFUNC1|stdinof a _function_]]
    
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
    
- [[miscellaneous-commands#^TEEREF|tee]], redirect to a file output of command(s) partway through a [[special-characters#^PIPEREF|pipe]]
    

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
    
- **$** (dollar sign) [[brief-introduction-to-regular-expressions#^DOLLARSIGNREF|_Anchor_]]
    
- **.** (dot) [[brief-introduction-to-regular-expressions#^REGEXDOT|Match single character]]
    
- ***** (asterisk) [[special-characters#^ASTERISKREF2|Any number of characters]]
    
- **[[brief-introduction-to-regular-expressions#^BRACKETSREF| ]** (brackets) [Enclose character set to match]]
    
- **\** (backslash) [[brief-introduction-to-regular-expressions#^REGEXBS|Escape]], interpret following character literally
    
- **\< ... \>** (angle brackets, _escaped_) [[brief-introduction-to-regular-expressions#^ANGLEBRAC|Word boundary]]
    
- [[brief-introduction-to-regular-expressions#^EXTREGEX|Extended]] REs
    
    **+** [[brief-introduction-to-regular-expressions#^PLUSREF|_Character match_]]
    
    **\{ \}** [[brief-introduction-to-regular-expressions#^ESCPCB|Escaped "curly" brackets]]
    
    **[[brief-introduction-to-regular-expressions#^POSIXREF|: :]** [POSIX character classes]]
    

[[internal-variables#^REPLYREF|$REPLY]], Default value associated with [[internal-commands-and-builtins#^READREF|read]] command

[[restricted-shells#^RESTRICTEDSHREF|Restricted shell]], shell (or script) with certain commands disabled

[[complex-functions-and-function-complexities#^RETURNREF|return]], command that terminates a [[functions#^FUNCTIONREF|function]]

[[miscellaneous-commands#^RUNPARTSREF|run-parts]]

- [[assorted-tips#^RUNPARTSREF2|Running scripts in sequence]], without user intervention
    

* * *

[[subshells#^SCOPEREF|Scope]] of a variable, definition

[[options#^INVOCATIONOPTIONSREF|Script options]], set at command line

[[assorted-tips#^LIBROUTINES|Scripting routines]], library of useful definitions and [[functions#^FUNCTIONREF|functions]]

[[internal-variables#^SECPROMPTREF|Secondary prompt]], **$PS2**

[[securityissues|Security issues]]

- [[system-and-administrative-commands#^NMAPREF|nmap]], _network mapper_ / port scanner
    
- [[system-and-administrative-commands#^SUDOREF|sudo]]
    
- [[gotchas#^SUIDSCR|_suid_ commands inside a script]]
    
- [[securityissues#^INFECTEDSCRIPTS1|Viruses, trojans, and worms]] in scripts
    
- [[securityissues#^SECURITYTIPS1|Writing secure scripts]]
    

[[Appendix C. A Sed and Awk Micro-Primer#^SEDREF|sed]], pattern-based programming language

- [[C.1. Sed#^SEDBASICTABLE|**Table**]], basic operators
    
- [[C.1. Sed#^SEDOPTABLE|**Table**]], examples of operators
    

[[testing-and-branching#^SELECTREF|select]], construct for menu building

- [[testing-and-branching#^INLISTOMIT|**in _list_** omitted]]
    

[[system-and-administrative-commands#^SEMAPHOREREF|Semaphore]]

[[loops#^NEEDSEMICOLON|Semicolon required]], when [[loops#^DOINREF|do]] _keyword_ is on first line of [[loops#^FORLOOPREF1|loop]]

- [[gotchas#^OMITSEMICOLON|When terminating _curly-bracketed_ code block]]
    

[[miscellaneous-commands#^SEQREF|seq]], Emit a sequence of integers. Equivalent to [[miscellaneous-commands#^JOTREF|jot]].

[[internal-commands-and-builtins#^SETREF|set]], Change value of internal script variables

- [[debugging#^UNDVARERR|set -u]], Abort script with error message if attempting to use an _undeclared_ variable.
    

[[Part 1. Introduction#^WHATSASCRIPT|Shell script]], definition of

[[shell-wrapper#^SHWRAPPER|Shell wrapper]], script embedding a command or utility

[[othertypesv#^SHIFTREF|shift]], reassigning _positional parameters_

[[internal-variables#^SHLVLREF|$SHLVL]], _shell level_, depth to which the shell (or script) is nested

[[internal-commands-and-builtins#^SHOPTREF|shopt]], change _shell options_

[[debugging#^SIGNALD|Signal]], a message sent to a process

Simulations

- [[generate-random-integer#^BROWNIANREF|Brownian motion]]
    
- [[generate-random-integer#^BROWNIANREF|Galton board]]
    
- [[colorizing#^HORSERACEREF|Horserace]]
    
- [[contributed-scripts#^LIFEREF|_Life_]], game of
    
- [[math-commands#^CANNONREF|PI]], approximating by firing cannonballs
    
- [[arrays#^STACKEX0|Pushdown _stack_]]
    

[[varsubn#^SNGLQUO|Single quotes]] (**' ... '**) _strong_ [[Chapter 5. Quoting#^QUOTINGREF|quoting]]

[[dev#^SOCKETREF|Socket]], a communication node associated with an I/O port

Sorting

- [[arrays#^BUBBLESORT|Bubble sort]]
    
- [[contributed-scripts#^INSERTIONSORT0|Insertion sort]]
    

[[internal-commands-and-builtins#^SOURCEREF|source]], execute a script or, within a script, import a file

- [[internal-commands-and-builtins#^SOURCEPARAMS|Passing positional parameters]]
    

_Spam_, dealing with

- [[communications-commands#^SPAMLOOKUP_0|_Example script_]]
    
- [[communications-commands#^ISSPAMMER_0|_Example script_]]
    
- [[contributed-scripts#^ISSPAMMER2_0|_Example script_]]
    
- [[contributed-scripts#^WHX0|_Example script_]]
    

[[special-characters#^SCHARLIST1|Special characters]]

Stack

- [[internal-variables#^STACKDEFREF|Definition]]
    
- Emulating a _push-down stack_, [[arrays#^STACKEX0|example script]]
    

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
    
- [[file-and-archiving-commands#^STRINGSREF|strings]] command, find printable strings in a binary or data file
    
- Substring extraction
    
    [[manipulating-strings#^SUBSTREXTR01|${string:position}]]
    
    [[manipulating-strings#^SUBSTREXTR02|${string:position:length}]]
    
    [[complex-commands#^EXPEXTRSUB|Using _expr_]]
    
- [[manipulating-strings#^SUBSTRINGINDEX2|Substring _index_]] (numerical position in string)
    
- [[manipulating-strings#^EXPRPAREN|Substring _matching_]], using [[complex-commands#^EXPRREF|expr]]
    
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
    

[[system-and-administrative-commands#^SUREF|su]] _Substitute user_, log on as a different user or as _root_

[[file-test-operators#^SUIDREF|suid]] (_set user id_) file flag

- [[gotchas#^SUIDSCR|_suid_ commands inside a script]], not advisable
    

[[basic-commands#^SYMLINKREF|Symbolic links]]

[[Chapter 31. Of Zeros and Nulls#^SWAPFILEREF|Swapfiles]]

* * *

[[tabexpansion|Tab completion]]

Table lookup, [[bash-ver2#^RESISTOR|script example]]

[[text-processing-commands#^TAILREF|tail]], _echo_ to stdout lines at the (tail) end of a text file

[[file-and-archiving-commands#^TARREF|tar]], archiving utility

[[miscellaneous-commands#^TEEREF|tee]], redirect to a file output of command(s) partway through a [[special-characters#^PIPEREF|pipe]]

[[system-and-administrative-commands#^TERMINALSSYS1|Terminals]]

- [[system-and-administrative-commands#^SETSERIALREF|setserial]]
    
- [[system-and-administrative-commands#^SETTERMREF|setterm]]
    
- [[system-and-administrative-commands#^STTYREF|stty]]
    
- [[terminal-control-commands#^TPUTREF|tput]]
    
- [[system-and-administrative-commands#^WALLREF|wall]]
    

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
    

[[text-processing-commands|Text and text file processing]]

[[time-date-commands|Time / Date]]

Timed input

- [[internal-commands-and-builtins#^READTIMED|Using _read -t_]]
    
- [[internal-variables#^STTYTO|Using _stty_]]
    
- [[internal-variables#^TIMINGLOOP|Using timing loop]]
    
- [[internal-variables#^TMOUTREF|Using $TMOUT]]
    

[[assorted-tips|Tips and hints]] for Bash scripts

- Array, [[assorted-tips#^RETARRAY|as _return value_ from a function]]
    
    _Associative_ array [[optimizations#^ASSOCARRTST|more efficient]] than a numerically-indexed array
    
- [[complex-functions-and-function-complexities#^CAPTURERETVAL|Capturing the return value]] of a function, using _echo_
    
- [[networkprogramming#^CGISCRIPT|_CGI_ programming]], using scripts for
    
- Comment blocks
    
    Using [[here-documents#^CBLOCK1|_anonymous here documents_]]
    
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
    
- [[assorted-tips#^RUNPARTSREF2|Running scripts in sequence]] without user intervention, using [[miscellaneous-commands#^RUNPARTSREF|run-parts]]
    
- Script [[assorted-tips#^SCRIPTASEMB|as embedded command]]
    
- Script _portability_
    
    [[assorted-tips#^SETPUM|Setting _path_ and _umask_]]
    
    [[assorted-tips#^WHATISREF3|Using _whatis_]]
    
- [[assorted-tips#^SETVAREMB|Setting script variable]] to a block of embedded _sed_ or _awk_ code
    
- Speeding up script execution by [[optimizations#^LCALL|disabling _unicode_]]
    
- Subshell variable, [[assorted-tips#^SUBSHTMP|accessing outside the subshell]]
    
- [[assorted-tips#^INTPARAM|Testing a variable]] to see if it contains only digits
    
- [[special-characters#^DEVNULLREDIRECT|Testing whether a command exists]], using [[internal-commands-and-builtins#^TYPEREF|type]]
    
- [[assorted-tips#^TRACKINGSCR|Tracking script usage]]
    
- [[process-substitution#^GOODREAD0|_while-read_ loop without a _subshell_]]
    
- [[assorted-tips#^WIDGETREF|Widgets]], invoking from a script
    

[[internal-variables#^TMOUTREF|$TMOUT]], Timeout interval

[[test-constructs#^TOKENREF|Token]], a symbol that may expand to a [[internal-commands-and-builtins#^KEYWORDREF|keyword]] or command

[[terminal-control-commands#^TPUTREF|tput]], terminal-control command

[[text-processing-commands#^TRREF|tr]], character translation filter

- [[text-processing-commands#^TRD2U|DOS to Unix text file conversion]]
    
- [[text-processing-commands#^TROPTIONS|Options]]
    
- [[contributed-scripts#^SOUNDEX0|Soundex]], _example script_
    
- [[text-processing-commands#^TRVARIANTS|Variants]]
    

[[debugging#^TRAPREF1|_Trap_]], specifying an action upon receipt of a [[debugging#^SIGNALD|signal]]

_Trinary (ternary)_ operator, _C_-style, **var>10?88:99**

- [[special-characters#^CSTRINARY|in _double-parentheses_ construct]]
    
- [[internal-commands-and-builtins#^EX46|in _let_ construct]]
    

[[internal-commands-and-builtins#^TRUEREF|true]], returns _successful_ (0) [[exit-status#^EXITSTATUSREF|exit status]]

[[typing-variables#^DECLARE1REF|typeset]] builtin

- [[typing-variables#^DECLAREOPSREF1|options]]
    

* * *

[[internal-variables#^UIDREF|$UID]], User ID number

[[aliases#^UNALIASREF|unalias]], to remove an [[aliases#^ALIASREF|alias]]

[[system-and-administrative-commands#^UNAMEREF|uname]], output system information

[[bash-ver4#^UNICODEREF|Unicode]], encoding standard for representing letters and symbols

- [[optimizations#^LCALL|Disabling _unicode_]] to optimize script
    

[[gotchas#^UNINITVAR|Uninitialized variables]]

[[text-processing-commands#^UNIQREF|uniq]], filter to remove duplicate lines from a sorted file

[[internal-commands-and-builtins#^UNSETREF|unset]], delete a shell variable

[[loops#^UNTILLOOPREF|until]] loop

_until [ condition-is-true ]; do_

* * *

_Variables_

- [[arrays#^ARRAYOPSVARS|Array operations on]]
    
- [[operators#^ASNOP1|Assignment]]
    
    [[varassignment#^EX15_0|_Script example_]]
    
    [[varassignment#^EX16_0|_Script example_]]
    
    [[varsubn#^VARUNSETTING|_Script example_]]
    
- [[internal-variables|_Bash_ internal variables]]
    
- [[assorted-tips#^SETVAREMB|Block of _sed_ or _awk_ code]], setting a variable to
    
- _C-style_ [[double-parentheses-construct#^PLUSPLUSREF|increment/decrement/trinary operations]]
    
- [[internal-commands-and-builtins#^SETREF|Change value of internal script variables]] using _set_
    
- [[typing-variables#^DECLARE1REF|declare]], to modify the properties of variables
    
- [[internal-commands-and-builtins#^UNSETREF|Deleting a shell variable]] using _unset_
    
- [[othertypesv#^ENVREF|Environmental]]
    
- [[parameter-substitution#^EXPREPL1|Expansion / Substring replacement]] operators
    
- [[indirect-references#^IVRREF|Indirect referencing]]
    
    _eval variable1=\$$variable2_
    
    [[indirect-references#^IVR2|Newer notation]]
    
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
    
- [[internal-commands-and-builtins#^UNSETREF|Unsetting]]
    
- [[untyped#^BVUNTYPED|Untyped]]
    

* * *

[[job-control-commands#^WAITREF|wait]], suspend script execution

- [[job-control-commands#^WAITHANG|To remedy script hang]]
    

[[varsubn#^DBLQUO|_Weak_ quoting]] **" ... "**

[[loops#^WHILELOOPREF|while]] loop

_while [ condition ]; do_

- [[loops#^WHLOOPC|C-style syntax]]
    
- [[loops#^WHILEFUNC|Calling a _function_ within _test_ brackets]]
    
- [[loops#^WHMULTCOND|Multiple conditions]]
    
- [[loops#^WHILENOBRACKETS|Omitting _test_ brackets]]
    
- [[loops#^WHILEREADREF2|_while read_]] construct
    
    [[process-substitution#^GOODREAD0|Avoiding a _subshell_]]
    

[[special-characters#^WHITESPACEREF|Whitespace]], spaces, tabs, and newline characters

- [[internal-variables#^IFSWS|$IFS defaults to]]
    
- [[gotchas#^WSBAD|Inappropriate use of]]
    
- [[here-documents#^INDENTEDLS|Preceding closing _limit string_]] in a _here document_, error
    
- [[special-characters#^WSBCOMM|Preceding script comments]]
    
- [[quoting-variables#^WSQUO|_Quoting_]], to preserve _whitespace_ within strings or variables
    
- [[brief-introduction-to-regular-expressions#^WSPOSIX|[:space:]]], _POSIX_ character class
    

[[system-and-administrative-commands#^WHOREF|who]], information about logged on users

- [[system-and-administrative-commands#^WREF|w]]
    
- [[system-and-administrative-commands#^WHOAMIREF|whoami]]
    
- [[system-and-administrative-commands#^LOGNAMEREF|logname]]
    

[[assorted-tips#^WIDGETREF|Widgets]]

[[globbing#^WILDCARDDEF|Wild card]] characters

- [[special-characters#^ASTERISKREF|Asterisk *]]
    
- In [[loops#^LIGLOB|_[list]_ constructs]]
    
- [[special-characters#^WILDCARDQU|Question mark ?]]
    
- [[globbing#^WDOTFILEWC|Will not match dot files]]
    

Word splitting

- [[quoting-variables#^WSPLITREF|Definition]]
    
- [[command-substitution#^CSWS|Resulting from _command substitution_]]
    

[[shell-wrapper#^SHWRAPPER|Wrapper]], shell

* * *

[[complex-commands#^XARGSREF|xargs]], Filter for grouping arguments

- [[complex-commands#^XARGSCURLYREF|Curly brackets]]
    
- [[complex-commands#^XARGSLIMARGS|Limiting arguments passed]]
    
- [[complex-commands#^XARGSLIMARGS|Options]]
    
- Processes arguments [[complex-commands#^XARGSONEATATIME|one at a time]]
    
- [[complex-commands#^XARGSWS|Whitespace]], handling
    

* * *

[[miscellaneous-commands#^YESREF|yes]]

- [[miscellaneous-commands#^YESEMU|Emulation]]
    

* * *

**-z** [[other-comparison-operators#^STRINGNULL|String is _null_]]

[[job-control-commands#^ZOMBIEREF|_Zombie_]], a process that has terminated, but not yet been [[job-control-commands#^KILLREF|killed]] by its [[internal-commands-and-builtins#^PARENTREF|parent]]

|ASCII Table|||