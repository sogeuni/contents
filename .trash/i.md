---
title: "Advanced Bash-Scripting Guide"
---

https://tldp.org/LDP/abs/html/index.html

## An in-depth exploration of the art of shell scripting

### Mendel Cooper

<[thegrendel.abs@gmail.com](mailto:thegrendel.abs@gmail.com)>

10  

10 Mar 2014  

|**Revision History**|   |   |
|:--|:--|:--|
|Revision 6.5|05 Apr 2012|Revised by: mc|
|'TUNGSTENBERRY' release|   |   |
|Revision 6.6|27 Nov 2012|Revised by: mc|
|'YTTERBIUMBERRY' release|   |   |
|Revision 10|10 Mar 2014|Revised by: mc|
|'PUBLICDOMAIN' release|   |   |

This tutorial assumes no previous knowledge of scripting or programming, yet progresses rapidly toward an intermediate/advanced level of instruction _. . . all the while sneaking in little nuggets of UNIX® wisdom and lore_. It serves as a textbook, a manual for self-study, and as a reference and source of knowledge on shell scripting techniques. The exercises and heavily-commented examples invite active reader participation, under the premise that **the only way to really learn scripting is to write scripts**.

This book is suitable for classroom use as a general introduction to programming concepts.

This document is herewith granted to the Public Domain. **No copyright!**
# Dedication

For Anita, the source of all the magic

## Table of Contents

[[Part 1. Introduction]]
[[why-shell|Chapter 1. Shell Programming!]]
[[abs/part1/sha-bang/index]]

[[abs/part2/index|Part 2. Basics]]
* [[special-characters]]
* [[variables]]
* [[Chapter 5. Quoting]]
* [[exit-status]]
* [[tests]]
* [[operations-and-related-topics]]

[[abs/part3/index|Part 3. Beyond the Basics]]
* [[another-look-at-variables]]
* [[manipulating-variables]]
* [[loops-and-branches]]
* [[command-substitution]]
* [[arithmetic-expansion]]
* [[recess-time]]

[[Part 4. Commands]]
* [[internal-commands-and-builtins|Internal Commands and Builtins]]
* [[Chapter 16. External Filters, Programs and Commands|External Filters, Programs and Commands]]
* [[system|System and Administrative Commands]]

[[Part 5. Advanced Topics]]
* [[regexp]]
* [[here-docs]]
* [[io-redirection]]
* [[subshells]]
* [[restricted-sh]]
* [[Chapter 23. Process Substitution]]
* [[functions]]
* [[Chapter 25. Aliases]]
* [[list-cons]]
* [[Chapter 27. Arrays]]
* [[ivr]]
* [[devproc]]
* [[networkprogramming]]
* [[Chapter 31. Of Zeros and Nulls]]
* [[debugging]]
* [[options]]
* [[gotchas]]
* [[scrstyle]]
* [[Chapter 36. Miscellany]]
* [[Chapter 37. Bash, versions 2, 3, and 4]]

[[Chapter 38. Endnotes]]
* [[38.1. Author's Note]]
* [[38.2. About the Author]]
* [[38.3. Where to Go For Help]]
* [[38.4. Tools Used to Produce This Book]]
* [[38.5. Credits]]
* [[38.6. Disclaimer]]

[[Bibliography|Bibliography]]
* [[contributed-scripts]]
* [[refcards]]
* [[Appendix C. A Sed and Awk Micro-Primer]]
	* [[C.1. Sed]]
	* [[C.2. Awk]]
* [[Appendix D. Parsing and Managing Pathnames]]
* [[exitcodes]
* [[ioredirintro]]
* [[Appendix G. Command-Line Options]]
	* [[standard-options]]
	* [[G.2. Bash Command-Line Options]]
* [[files]]
* [[systemdirs]]
* [[tabexpansion]]
* [[localization]]
* [[histcommands]]
* [[sample-bashrc]]
* [[Appendix N. Converting DOS Batch Files to Shell Scripts]]
* [[exercises]]
	* [[scriptanalysis]]
	* [[writingscripts]]
* [[revisionhistory]]
* [[mirrorsites]]
* [[Appendix R. To Do List]]
* [[Appendix S. Copyright]]
* [[Appendix T. ASCII Table]]

[[xrefindex|Index]]

## List of Tables

* [[operator-precedence#^1|8-1. Operator Precedence]]
* 15-1. [[job-control-commands#^JOBIDTABLE|Job identifiers]]

33-1. [[options#^AEN19601|Bash options]]

36-1. [[colorizing#^AEN20327|Numbers representing colors in Escape Sequences]]

B-1. [[refcards#^AEN22402|Special Shell Variables]]

B-2. [[refcards#^AEN22473|TEST Operators: Binary Comparison]]

B-3. [[refcards#^AEN22593|TEST Operators: Files]]

B-4. [[refcards#^AEN22728|Parameter Substitution and Expansion]]

B-5. [[refcards#^AEN22828|String Operations]]

B-6. [[refcards#^AEN22979|Miscellaneous Constructs]]

C-1. [[C.1. Sed#^AEN23200|Basic sed operators]]

C-2. [[C.1. Sed#^AEN23271|Examples of sed operators]]

E-1. [[exitcodes#^AEN23549|_Reserved_ Exit Codes]]

N-1. [[Appendix N. Converting DOS Batch Files to Shell Scripts#^AEN24336|Batch file keywords / variables / operators, and their shell equivalents]]

N-2. [[Appendix N. Converting DOS Batch Files to Shell Scripts#^AEN24545|DOS commands and their UNIX equivalents]]

P-1. [[revisionhistory#^AEN25364|Revision History]]

**List of Examples**

2-1. [[abs/part1/sha-bang/index#^EX1|_cleanup_: A script to clean up log files in /var/log]]

2-2. [[abs/part1/sha-bang/index#^EX1A|_cleanup_: An improved clean-up script]]

2-3. [[abs/part1/sha-bang/index#^EX2|_cleanup_: An enhanced and generalized version of above scripts.]]

3-1. [[special-characters#^EX8|Code blocks and I/O redirection]]

3-2. [[special-characters#^RPMCHECK|Saving the output of a code block to a file]]

3-3. [[special-characters#^BGLOOP|Running a loop in the background]]

3-4. [[special-characters#^EX58|Backup of all files changed in last day]]

4-1. [[varsubn#^EX9|Variable assignment and substitution]]

4-2. [[varassignment#^EX15|Plain Variable Assignment]]

4-3. [[varassignment#^EX16|Variable Assignment, plain and fancy]]

4-4. [[untyped#^INTORSTRING|Integer or string?]]

4-5. [[othertypesv#^EX17|Positional Parameters]]

4-6. [[othertypesv#^EX18|_wh_, _whois_ domain name lookup]]

4-7. [[othertypesv#^EX19|Using _shift_]]

5-1. [[quoting-variables#^WEIRDVARS|Echoing Weird Variables]]

5-2. [[escaping#^ESCAPED|Escaped Characters]]

5-3. [[escaping#^BASHEK|Detecting key-presses]]

6-1. [[exit-status#^EX5|exit / exit status]]

6-2. [[exit-status#^NEGCOND|Negating a condition using !]]

7-1. [[test-constructs#^EX10|What is truth?]]

7-2. [[test-constructs#^EX11|Equivalence of _test_, /usr/bin/test, [ ], and /usr/bin/[]]

7-3. [[test-constructs#^ARITHTESTS|Arithmetic Tests using (( ))]]

7-4. [[file-test-operators#^BROKENLINK|Testing for broken links]]

7-5. [[other-comparison-operators#^EX13|Arithmetic and string comparisons]]

7-6. [[other-comparison-operators#^STRTEST|Testing whether a string is _null_]]

7-7. [[other-comparison-operators#^EX14|_zmore_]]

8-1. [[operators#^GCD|Greatest common divisor]]

8-2. [[operators#^ARITHOPS|Using Arithmetic Operations]]

8-3. [[operators#^ANDOR|Compound Condition Tests Using && and ||]]

8-4. [[numerical-constants#^NUMBERS|Representation of numerical constants]]

8-5. [[double-parentheses-construct#^CVARS|C-style manipulation of variables]]

9-1. [[internal-variables#^IFSH|$IFS and whitespace]]

9-2. [[internal-variables#^TMDIN|Timed Input]]

9-3. [[internal-variables#^TIMEOUT|Once more, timed input]]

9-4. [[internal-variables#^TOUT|Timed _read_]]

9-5. [[internal-variables#^AMIROOT|Am I root?]]

9-6. [[internal-variables#^ARGLIST|_arglist_: Listing arguments with $* and $@]]

9-7. [[internal-variables#^INCOMPAT|Inconsistent $* and $@ behavior]]

9-8. [[internal-variables#^IFSEMPTY|$* and $@ when $IFS is empty]]

9-9. [[internal-variables#^USCREF|Underscore variable]]

9-10. [[typing-variables#^EX20|Using _declare_ to type variables]]

9-11. [[generate-random-integer#^EX21|Generating random numbers]]

9-12. [[generate-random-integer#^PICKCARD|Picking a random card from a deck]]

9-13. [[generate-random-integer#^BROWNIAN|Brownian Motion Simulation]]

9-14. [[generate-random-integer#^RANDOMBETWEEN|Random between values]]

9-15. [[generate-random-integer#^RANDOMTEST|Rolling a single die with RANDOM]]

9-16. [[generate-random-integer#^SEEDINGRANDOM|Reseeding RANDOM]]

9-17. [[generate-random-integer#^RANDOM2|Pseudorandom numbers, using]] [[C.2. Awk#^AWKREF|awk]]

10-1. [[manipulating-strings#^PARAGRAPHSPACE|Inserting a blank line between paragraphs in a text file]]

10-2. [[manipulating-strings#^RANDSTRING|Generating an 8-character "random" string]]

10-3. [[manipulating-strings#^CVT|Converting graphic file formats, with filename change]]

10-4. [[manipulating-strings#^RA2OGG|Converting streaming audio files to _ogg_]]

10-5. [[manipulating-strings#^GETOPTSIMPLE|Emulating _getopt_]]

10-6. [[manipulating-strings#^SUBSTRINGEX|Alternate ways of extracting and locating substrings]]

10-7. [[parameter-substitution#^EX6|Using parameter substitution and error messages]]

10-8. [[parameter-substitution#^USAGEMESSAGE|Parameter substitution and "usage" messages]]

10-9. [[parameter-substitution#^LENGTH|Length of a variable]]

10-10. [[parameter-substitution#^PATTMATCHING|Pattern matching in parameter substitution]]

10-11. [[parameter-substitution#^RFE|Renaming file extensions:]]

10-12. [[parameter-substitution#^EX7|Using pattern matching to parse arbitrary strings]]

10-13. [[parameter-substitution#^VARMATCH|Matching patterns at prefix or suffix of string]]

11-1. [[loops#^EX22|Simple _for_ loops]]

11-2. [[loops#^EX22A|_for_ loop with two parameters in each [list] element]]

11-3. [[loops#^FILEINFO|_Fileinfo:_ operating on a file list contained in a variable]]

11-4. [[loops#^FILEINFO01|Operating on a parameterized file list]]

11-5. [[loops#^LISTGLOB|Operating on files with a _for_ loop]]

11-6. [[loops#^EX23|Missing **in [list]** in a _for_ loop]]

11-7. [[loops#^FORLOOPCMD|Generating the **[list]** in a _for_ loop with command substitution]]

11-8. [[loops#^BINGREP|A _grep_ replacement for binary files]]

11-9. [[loops#^USERLIST|Listing all users on the system]]

11-10. [[loops#^FINDSTRING|Checking all the binaries in a directory for authorship]]

11-11. [[loops#^SYMLINKS|Listing the _symbolic links_ in a directory]]

11-12. [[loops#^SYMLINKS2|Symbolic links in a directory, saved to a file]]

11-13. [[loops#^FORLOOPC|A C-style _for_ loop]]

11-14. [[loops#^EX24|Using _efax_ in batch mode]]

11-15. [[loops#^EX25|Simple _while_ loop]]

11-16. [[loops#^EX26|Another _while_ loop]]

11-17. [[loops#^EX26A|_while_ loop with multiple conditions]]

11-18. [[loops#^WHLOOPC|C-style syntax in a _while_ loop]]

11-19. [[loops#^EX27|_until_ loop]]

11-20. [[nested-loops#^NESTEDLOOP|Nested Loop]]

11-21. [[loop-control#^EX28|Effects of _break_ and **continue** in a loop]]

11-22. [[loop-control#^BREAKLEVELS|Breaking out of multiple loop levels]]

11-23. [[loop-control#^CONTINUELEVELS|Continuing at a higher loop level]]

11-24. [[loop-control#^CONTINUENEX|Using _continue N_ in an actual task]]

11-25. [[testing-and-branching#^EX29|Using _case_]]

11-26. [[testing-and-branching#^EX30|Creating menus using _case_]]

11-27. [[testing-and-branching#^CASECMD|Using _command substitution_ to generate the _case_ variable]]

11-28. [[testing-and-branching#^MATCHSTRING|Simple string matching]]

11-29. [[testing-and-branching#^ISALPHA|Checking for alphabetic input]]

11-30. [[testing-and-branching#^EX31|Creating menus using _select_]]

11-31. [[testing-and-branching#^EX32|Creating menus using _select_ in a function]]

12-1. [[command-substitution#^STUPSCR|Stupid script tricks]]

12-2. [[command-substitution#^CSUBLOOP|Generating a variable from a loop]]

12-3. [[command-substitution#^AGRAM2|Finding anagrams]]

15-1. [[internal-commands-and-builtins#^SPAWNSCR|A script that spawns multiple instances of itself]]

15-2. [[internal-commands-and-builtins#^EX47|_printf_ in action]]

15-3. [[internal-commands-and-builtins#^EX36|Variable assignment, using _read_]]

15-4. [[internal-commands-and-builtins#^READNOVAR|What happens when _read_ has no variable]]

15-5. [[internal-commands-and-builtins#^READR|Multi-line input to _read_]]

15-6. [[internal-commands-and-builtins#^ARROWDETECT|Detecting the arrow keys]]

15-7. [[internal-commands-and-builtins#^READREDIR|Using _read_ with]] [[io-redirection#^IOREDIRREF|file redirection]]

15-8. [[internal-commands-and-builtins#^READPIPE|Problems reading from a pipe]]

15-9. [[internal-commands-and-builtins#^EX37|Changing the current working directory]]

15-10. [[internal-commands-and-builtins#^EX46|Letting _let_ do arithmetic.]]

15-11. [[internal-commands-and-builtins#^EX43|Showing the effect of _eval_]]

15-12. [[internal-commands-and-builtins#^ARRCHOICE|Using _eval_ to select among variables]]

15-13. [[internal-commands-and-builtins#^ECHOPARAMS|_Echoing_ the _command-line parameters_]]

15-14. [[internal-commands-and-builtins#^EX44|Forcing a log-off]]

15-15. [[internal-commands-and-builtins#^ROT14|A version of _rot13_]]

15-16. [[internal-commands-and-builtins#^EX34|Using _set_ with positional parameters]]

15-17. [[internal-commands-and-builtins#^REVPOSPARAMS|Reversing the positional parameters]]

15-18. [[internal-commands-and-builtins#^SETPOS|Reassigning the positional parameters]]

15-19. [[internal-commands-and-builtins#^UNS|"Unsetting" a variable]]

15-20. [[internal-commands-and-builtins#^COLTOTALER3|Using _export_ to pass a variable to an embedded _awk_ script]]

15-21. [[internal-commands-and-builtins#^EX33|Using _getopts_ to read the options/arguments passed to a script]]

15-22. [[internal-commands-and-builtins#^EX38|"Including" a data file]]

15-23. [[internal-commands-and-builtins#^SELFSOURCE|A (useless) script that sources itself]]

15-24. [[internal-commands-and-builtins#^EX54|Effects of _exec_]]

15-25. [[internal-commands-and-builtins#^SELFEXEC|A script that _exec's_ itself]]

15-26. [[job-control-commands#^EX39|Waiting for a process to finish before proceeding]]

15-27. [[job-control-commands#^SELFDESTRUCT|A script that kills itself]]

16-1. [[basic#^EX40|Using _ls_ to create a table of contents for burning a CDR disk]]

16-2. [[basic#^HELLOL|Hello or Good-bye]]

16-3. [[complex-commands#^EX57|_Badname_, eliminate file names in current directory containing bad characters and]] [[special-characters#^WHITESPACEREF|whitespace]].

16-4. [[complex-commands#^IDELETE|Deleting a file by its _inode_ number]]

16-5. [[complex-commands#^EX41|Logfile: Using _xargs_ to monitor system log]]

16-6. [[complex-commands#^EX42|Copying files in current directory to another]]

16-7. [[complex-commands#^KILLBYNAME|Killing processes by name]]

16-8. [[complex-commands#^WF2|Word frequency analysis using _xargs_]]

16-9. [[complex-commands#^EX45|Using _expr_]]

16-10. [[time-date-commands#^EX51|Using _date_]]

16-11. [[time-date-commands#^DATECALC|_Date_ calculations]]

16-12. [[textproc#^WF|Word Frequency Analysis]]

16-13. [[textproc#^SCRIPTDETECTOR|Which files are scripts?]]

16-14. [[textproc#^RND|Generating 10-digit random numbers]]

16-15. [[textproc#^EX12|Using _tail_ to monitor the system log]]

16-16. [[textproc#^FROMSH|Printing out the _From_ lines in stored e-mail messages]]

16-17. [[textproc#^GRP|Emulating _grep_ in a script]]

16-18. [[textproc#^CWSOLVER|Crossword puzzle solver]]

16-19. [[textproc#^DICTLOOKUP|Looking up definitions in Webster's 1913 Dictionary]]

16-20. [[textproc#^LOOKUP|Checking words in a list for validity]]

16-21. [[textproc#^EX49|_toupper_: Transforms a file to all uppercase.]]

16-22. [[textproc#^LOWERCASE|_lowercase_: Changes all filenames in working directory to lowercase.]]

16-23. [[textproc#^DU|_du_: DOS to UNIX text file conversion.]]

16-24. [[textproc#^ROT13|_rot13_: ultra-weak encryption.]]

16-25. [[textproc#^CRYPTOQUOTE|Generating "Crypto-Quote" Puzzles]]

16-26. [[textproc#^EX50|Formatted file listing.]]

16-27. [[textproc#^COL|Using _column_ to format a directory listing]]

16-28. [[textproc#^LNUM|_nl_: A self-numbering script.]]

16-29. [[textproc#^MANVIEW|_manview_: Viewing formatted manpages]]

16-30. [[filearchiv#^EX48|Using _cpio_ to move a directory tree]]

16-31. [[filearchiv#^DERPM|Unpacking an _rpm_ archive]]

16-32. [[filearchiv#^STRIPC|Stripping comments from C program files]]

16-33. [[filearchiv#^WHAT|Exploring /usr/X11R6/bin]]

16-34. [[filearchiv#^WSTRINGS|An "improved" _strings_ command]]

16-35. [[filearchiv#^FILECOMP|Using _cmp_ to compare two files within a script.]]

16-36. [[filearchiv#^EX35|_basename_ and _dirname_]]

16-37. [[filearchiv#^SPLITCOPY|A script that copies itself in sections]]

16-38. [[filearchiv#^FILEINTEGRITY|Checking file integrity]]

16-39. [[filearchiv#^EX52|Uudecoding encoded files]]

16-40. [[communications#^SPAMLOOKUP|Finding out where to report a spammer]]

16-41. [[communications#^ISSPAMMER|Analyzing a spam domain]]

16-42. [[communications#^QUOTEFETCH|Getting a stock quote]]

16-43. [[communications#^FC4UPD|Updating FC4]]

16-44. [[communications#^REMOTE|Using _ssh_]]

16-45. [[communications#^SELFMAILER|A script that mails itself]]

16-46. [[mathc#^PRIMES2|Generating prime numbers]]

16-47. [[mathc#^MONTHLYPMT|Monthly Payment on a Mortgage]]

16-48. [[mathc#^BASE|Base Conversion]]

16-49. [[mathc#^ALTBC|Invoking _bc_ using a _here document_]]

16-50. [[mathc#^CANNON|Calculating PI]]

16-51. [[mathc#^HEXCONVERT|Converting a decimal number to hexadecimal]]

16-52. [[mathc#^FACTR|Factoring]]

16-53. [[mathc#^HYPOT|Calculating the hypotenuse of a triangle]]

16-54. [[extmisc#^EX53|Using _seq_ to generate loop arguments]]

16-55. [[extmisc#^LETTERCOUNT|Letter Count"]]

16-56. [[extmisc#^EX33A|Using _getopt_ to parse command-line options]]

16-57. [[extmisc#^SELFCOPY|A script that copies itself]]

16-58. [[extmisc#^EXERCISINGDD|Exercising _dd_]]

16-59. [[extmisc#^DDKEYPRESS|Capturing Keystrokes]]

16-60. [[extmisc#^RPSDCARD|Preparing a bootable SD card for the _Raspberry Pi_]]

16-61. [[extmisc#^BLOTOUT|Securely deleting a file]]

16-62. [[extmisc#^TEMPFILENAME|Filename generator]]

16-63. [[extmisc#^UNITCONVERSION|Converting meters to miles]]

16-64. [[extmisc#^M4|Using _m4_]]

17-1. [[system#^SETNEWPW|Setting a new password]]

17-2. [[system#^ERASE|Setting an _erase_ character]]

17-3. [[system#^SECRETPW|_secret password_: Turning off terminal echoing]]

17-4. [[system#^KEYPRESS|Keypress detection]]

17-5. [[system#^ISCAN|Checking a remote server for _identd_]]

17-6. [[system#^KILLPROCESS|_pidof_ helps kill a process]]

17-7. [[system#^ISOMOUNTREF|Checking a CD image]]

17-8. [[system#^CREATEFS|Creating a filesystem in a file]]

17-9. [[system#^ADDDRV|Adding a new hard drive]]

17-10. [[system#^ROT13A|Using _umask_ to hide an output file from prying eyes]]

17-11. [[system#^BACKLIGHT|_Backlight_: changes the brightness of the (laptop) screen backlight]]

17-12. [[sysscripts#^EX55|_killall_, from /etc/rc.d/init.d]]

19-1. [[here-docs#^EX70|_broadcast_: Sends message to everyone logged in]]

19-2. [[here-docs#^EX69|_dummyfile_: Creates a 2-line dummy file]]

19-3. [[here-docs#^EX71|Multi-line message using _cat_]]

19-4. [[here-docs#^EX71A|Multi-line message, with tabs suppressed]]

19-5. [[here-docs#^EX71B|Here document with replaceable parameters]]

19-6. [[here-docs#^EX72|Upload a file pair to _Sunsite_ incoming directory]]

19-7. [[here-docs#^EX71C|Parameter substitution turned off]]

19-8. [[here-docs#^GENERATESCRIPT|A script that generates another script]]

19-9. [[here-docs#^HF|Here documents and functions]]

19-10. [[here-docs#^ANONHEREDOC|"Anonymous" Here Document]]

19-11. [[here-docs#^COMMENTBLOCK|Commenting out a block of code]]

19-12. [[here-docs#^SELFDOCUMENT|A self-documenting script]]

19-13. [[x17837#^PREPENDEX|Prepending a line to a file]]

19-14. [[x17837#^MAILBOXGREP|Parsing a mailbox]]

20-1. [[20.1. Using _exec_#^REDIR1|Redirecting stdin using _exec_]]

20-2. [[20.1. Using _exec_#^REASSIGNSTDOUT|Redirecting stdout using _exec_]]

20-3. [[20.1. Using _exec_#^UPPERCONV|Redirecting both stdin and stdout in the same script with _exec_]]

20-4. [[20.1. Using _exec_#^AVOIDSUBSHELL|Avoiding a subshell]]

20-5. [[redircb#^REDIR2|Redirected _while_ loop]]

20-6. [[redircb#^REDIR2A|Alternate form of redirected _while_ loop]]

20-7. [[redircb#^REDIR3|Redirected _until_ loop]]

20-8. [[redircb#^REDIR4|Redirected _for_ loop]]

20-9. [[redircb#^REDIR4A|Redirected _for_ loop (both stdin and stdout redirected)]]

20-10. [[redircb#^REDIR5|Redirected _if/then_ test]]

20-11. [[redircb#^NAMESDATA|Data file _names.data_ for above examples]]

20-12. [[redirapps#^LOGEVENTS|Logging events]]

21-1. [[subshells#^SUBSHELL|Variable scope in a subshell]]

21-2. [[subshells#^ALLPROFS|List User Profiles]]

21-3. [[subshells#^PARALLEL-PROCESSES|Running parallel processes in subshells]]

22-1. [[restricted-sh#^RESTRICTED|Running a script in restricted mode]]

23-1. [[Chapter 23. Process Substitution#^WRPS|Code block redirection without forking]]

23-2. [[Chapter 23. Process Substitution#^PSUBP|Redirecting the output of _process substitution_ into a loop.]]

24-1. [[functions#^EX59|Simple functions]]

24-2. [[complexfunct#^EX60|Function Taking Parameters]]

24-3. [[complexfunct#^FUNCCMDLINEARG|Functions and command-line args passed to the script]]

24-4. [[complexfunct#^INDFUNC|Passing an indirect reference to a function]]

24-5. [[complexfunct#^DEREFERENCECL|Dereferencing a parameter passed to a function]]

24-6. [[complexfunct#^REFPARAMS|Again, dereferencing a parameter passed to a function]]

24-7. [[complexfunct#^MAX|Maximum of two numbers]]

24-8. [[complexfunct#^EX61|Converting numbers to Roman numerals]]

24-9. [[complexfunct#^RETURNTEST|Testing large return values in a function]]

24-10. [[complexfunct#^MAX2|Comparing two large integers]]

24-11. [[complexfunct#^REALNAME|Real name from username]]

24-12. [[localvar#^EX62|Local variable visibility]]

24-13. [[localvar#^RECURSIONDEMO|Demonstration of a simple recursive function]]

24-14. [[localvar#^RECURSIONDEMO2|Another simple demonstration]]

24-15. [[localvar#^EX63|Recursion, using a local variable]]

24-16. [[recurnolocvar#^FIBO|_The Fibonacci Sequence_]]

24-17. [[recurnolocvar#^HANOI|_The Towers of Hanoi_]]

25-1. [[Chapter 25. Aliases#^AL|Aliases within a script]]

25-2. [[Chapter 25. Aliases#^UNAL|_unalias_: Setting and unsetting an alias]]

26-1. [[list-cons#^EX64|Using an _and list_ to test for command-line arguments]]

26-2. [[list-cons#^ANDLIST2|Another command-line arg test using an _and list_]]

26-3. [[list-cons#^EX65|Using _or lists_ in combination with an _and list_]]

27-1. [[Chapter 27. Arrays#^EX66|Simple array usage]]

27-2. [[Chapter 27. Arrays#^POEM|Formatting a poem]]

27-3. [[Chapter 27. Arrays#^ARRAYOPS|Various array operations]]

27-4. [[Chapter 27. Arrays#^ARRAYSTROPS|String operations on arrays]]

27-5. [[Chapter 27. Arrays#^SCRIPTARRAY|Loading the contents of a script into an array]]

27-6. [[Chapter 27. Arrays#^EX67|Some special properties of arrays]]

27-7. [[Chapter 27. Arrays#^EMPTYARRAY|Of empty arrays and empty elements]]

27-8. [[Chapter 27. Arrays#^ARRAYASSIGN|Initializing arrays]]

27-9. [[Chapter 27. Arrays#^COPYARRAY|Copying and concatenating arrays]]

27-10. [[Chapter 27. Arrays#^ARRAYAPPEND|More on concatenating arrays]]

27-11. [[Chapter 27. Arrays#^BUBBLE|The Bubble Sort]]

27-12. [[Chapter 27. Arrays#^EMBARR|Embedded arrays and indirect references]]

27-13. [[Chapter 27. Arrays#^EX68|The Sieve of Eratosthenes]]

27-14. [[Chapter 27. Arrays#^EX68A|The Sieve of Eratosthenes, Optimized]]

27-15. [[Chapter 27. Arrays#^STACKEX|Emulating a push-down stack]]

27-16. [[Chapter 27. Arrays#^QFUNCTION|Complex array application: _Exploring a weird mathematical series_]]

27-17. [[Chapter 27. Arrays#^TWODIM|Simulating a two-dimensional array, then tilting it]]

28-1. [[ivr#^INDREF|Indirect Variable References]]

28-2. [[ivr#^COLTOTALER2|Passing an indirect reference to _awk_]]

29-1. [[devref1#^DEVTCP|Using /dev/tcp for troubleshooting]]

29-2. [[devref1#^MUSICSCR|Playing music]]

29-3. [[procref1#^PIDID|Finding the process associated with a PID]]

29-4. [[procref1#^CONSTAT|On-line connect status]]

30-1. [[networkprogramming#^TESTCGI|Print the server environment]]

30-2. [[networkprogramming#^IPADDRESSES|IP addresses]]

31-1. [[Chapter 31. Of Zeros and Nulls#^COOKIES|Hiding the cookie jar]]

31-2. [[Chapter 31. Of Zeros and Nulls#^EX73|Setting up a swapfile using /dev/zero]]

31-3. [[Chapter 31. Of Zeros and Nulls#^RAMDISK|Creating a ramdisk]]

32-1. [[debugging#^EX74|A buggy script]]

32-2. [[debugging#^MISSINGKEYWORD|Missing]] [[internal-commands-and-builtins#^KEYWORDREF|keyword]]

32-3. [[debugging#^EX75|_test24_: another buggy script]]

32-4. [[debugging#^ASSERT|Testing a condition with an _assert_]]

32-5. [[debugging#^EX76|Trapping at exit]]

32-6. [[debugging#^ONLINE|Cleaning up after **Control-C**]]

32-7. [[debugging#^PROGRESSBAR2|A Simple Implementation of a Progress Bar]]

32-8. [[debugging#^VARTRACE|Tracing a variable]]

32-9. [[debugging#^MULTIPLEPROC|Running multiple processes (on an SMP box)]]

34-1. [[gotchas#^BADOP|Numerical and string comparison are not equivalent]]

34-2. [[gotchas#^SUBPIT|Subshell Pitfalls]]

34-3. [[gotchas#^BADREAD|Piping the output of _echo_ to a _read_]]

36-1. [[wrapper#^EX3|_shell wrapper_]]

36-2. [[wrapper#^EX4|A slightly more complex _shell wrapper_]]

36-3. [[wrapper#^LOGGINGWRAPPER|A generic _shell wrapper_ that writes to a logfile]]

36-4. [[wrapper#^PRASC|A _shell wrapper_ around an awk script]]

36-5. [[wrapper#^COLTOTALER|A _shell wrapper_ around another awk script]]

36-6. [[wrapper#^EX56|Perl embedded in a _Bash_ script]]

36-7. [[wrapper#^BASHANDPERL|Bash and Perl scripts combined]]

36-8. [[wrapper#^EX56PY|Python embedded in a _Bash_ script]]

36-9. [[wrapper#^SPEECH0|A script that speaks]]

36-10. [[recursionsct#^RECURSE|A (useless) script that recursively calls itself]]

36-11. [[recursionsct#^PBOOK|A (useful) script that recursively calls itself]]

36-12. [[recursionsct#^USRMNT|Another (useful) script that recursively calls itself]]

36-13. [[colorizing#^EX30A|A "colorized" address database]]

36-14. [[colorizing#^DRAW-BOX|Drawing a box]]

36-15. [[colorizing#^COLORECHO|Echoing colored text]]

36-16. [[colorizing#^HORSERACE|A "horserace" game]]

36-17. [[36.7. Assorted Tips#^PROGRESSBAR|A Progress Bar]]

36-18. [[36.7. Assorted Tips#^MULTIPLICATION|Return value trickery]]

36-19. [[36.7. Assorted Tips#^SUMPRODUCT|Even more return value trickery]]

36-20. [[36.7. Assorted Tips#^ARRFUNC|Passing and returning arrays]]

36-21. [[36.7. Assorted Tips#^AGRAM|Fun with anagrams]]

36-22. [[36.7. Assorted Tips#^DIALOG|Widgets invoked from a shell script]]

36-23. [[36.9. Portability Issues#^TESTSUITE|Test Suite]]

37-1. [[37.1. Bash, version 2#^EX77|String expansion]]

37-2. [[37.1. Bash, version 2#^EX78|Indirect variable references - the new way]]

37-3. [[37.1. Bash, version 2#^RESISTOR|Simple database application, using indirect variable referencing]]

37-4. [[37.1. Bash, version 2#^CARDS|Using arrays and other miscellaneous trickery to deal four random hands from a deck of cards]]

37-5. [[bashver4#^FETCHADDRESS|A simple address database]]

37-6. [[bashver4#^FETCHADDRESS2|A somewhat more elaborate address database]]

37-7. [[bashver4#^CASE4|Testing characters]]

37-8. [[bashver4#^READN|Reading N characters]]

37-9. [[bashver4#^HERECOMMSUB|Using a _here document_ to set a variable]]

37-10. [[bashver4#^LASTPIPEOPT|Piping input to a]] [[internal-commands-and-builtins#^READREF|read]]

37-11. [[bashver4#^NEGARRAY|Negative array indices]]

37-12. [[bashver4#^NEGOFFSET|Negative parameter in string-extraction construct]]

A-1. [[contributed-scripts#^MAILFORMAT|_mailformat_: Formatting an e-mail message]]

A-2. [[contributed-scripts#^RN|_rn_: A simple-minded file renaming utility]]

A-3. [[contributed-scripts#^BLANKRENAME|_blank-rename_: Renames filenames containing blanks]]

A-4. [[contributed-scripts#^ENCRYPTEDPW|_encryptedpw_: Uploading to an ftp site, using a locally encrypted password]]

A-5. [[contributed-scripts#^COPYCD|_copy-cd_: Copying a data CD]]

A-6. [[contributed-scripts#^COLLATZ|Collatz series]]

A-7. [[contributed-scripts#^DAYSBETWEEN|_days-between_: Days between two dates]]

A-8. [[contributed-scripts#^MAKEDICT|Making a _dictionary_]]

A-9. [[contributed-scripts#^SOUNDEX|Soundex conversion]]

A-10. [[contributed-scripts#^LIFESLOW|_Game of Life_]]

A-11. [[contributed-scripts#^GEN0DATA|Data file for _Game of Life_]]

A-12. [[contributed-scripts#^BEHEAD|_behead_: Removing mail and news message headers]]

A-13. [[contributed-scripts#^PW|_password_: Generating random 8-character passwords]]

A-14. [[contributed-scripts#^FIFO|_fifo_: Making daily backups, using named pipes]]

A-15. [[contributed-scripts#^PRIMES|Generating prime numbers using the modulo operator]]

A-16. [[contributed-scripts#^TREE|_tree_: Displaying a directory tree]]

A-17. [[contributed-scripts#^TREE2|_tree2_: Alternate directory tree script]]

A-18. [[contributed-scripts#^STRING|_string functions_: C-style string functions]]

A-19. [[contributed-scripts#^DIRECTORYINFO|Directory information]]

A-20. [[contributed-scripts#^HASHLIB|Library of hash functions]]

A-21. [[contributed-scripts#^HASHEXAMPLE|Colorizing text using hash functions]]

A-22. [[contributed-scripts#^HASHEX2|More on hash functions]]

A-23. [[contributed-scripts#^USBINST|Mounting USB keychain storage devices]]

A-24. [[contributed-scripts#^TOHTML|Converting to HTML]]

A-25. [[contributed-scripts#^ARCHIVWEBLOGS|Preserving weblogs]]

A-26. [[contributed-scripts#^PROTECTLITERAL|Protecting literal strings]]

A-27. [[contributed-scripts#^UNPROTECTLITERAL|Unprotecting literal strings]]

A-28. [[contributed-scripts#^ISSPAMMER2|Spammer Identification]]

A-29. [[contributed-scripts#^WHX|Spammer Hunt]]

A-30. [[contributed-scripts#^WGETTER2|Making _wget_ easier to use]]

A-31. [[contributed-scripts#^BASHPODDER|A _podcasting_ script]]

A-32. [[contributed-scripts#^NIGHTLYBACKUP|Nightly backup to a firewire HD]]

A-33. [[contributed-scripts#^CDLL|An expanded _cd_ command]]

A-34. [[contributed-scripts#^SOUNDCARDON|A soundcard setup script]]

A-35. [[contributed-scripts#^FINDSPLIT|Locating split paragraphs in a text file]]

A-36. [[contributed-scripts#^INSERTIONSORT|Insertion sort]]

A-37. [[contributed-scripts#^STDDEV|Standard Deviation]]

A-38. [[contributed-scripts#^PADSW|A _pad_ file generator for shareware authors]]

A-39. [[contributed-scripts#^MANED|A _man page_ editor]]

A-40. [[contributed-scripts#^PETALS|Petals Around the Rose]]

A-41. [[contributed-scripts#^QKY|Quacky: a Perquackey-type word game]]

A-42. [[contributed-scripts#^NIM|Nim]]

A-43. [[contributed-scripts#^STOPWATCH|A command-line stopwatch]]

A-44. [[contributed-scripts#^HOMEWORK|An all-purpose shell scripting homework assignment solution]]

A-45. [[contributed-scripts#^KTOUR|The Knight's Tour]]

A-46. [[contributed-scripts#^MSQUARE|Magic Squares]]

A-47. [[contributed-scripts#^FIFTEEN|Fifteen Puzzle]]

A-48. [[contributed-scripts#^HANOI2|_The Towers of Hanoi, graphic version_]]

A-49. [[contributed-scripts#^HANOI2A|_The Towers of Hanoi, alternate graphic version_]]

A-50. [[contributed-scripts#^USEGETOPT|An alternate version of the]] [[manipulating-strings#^GETOPTSIMPLE|getopt-simple.sh]] script

A-51. [[contributed-scripts#^USEGETOPT2|The version of the _UseGetOpt.sh_ example used in the]] [[tabexpansion|Tab Expansion appendix]]

A-52. [[contributed-scripts#^SHOWALLC|Cycling through all the possible color backgrounds]]

A-53. [[contributed-scripts#^SAMORSE|Morse Code Practice]]

A-54. [[contributed-scripts#^BASE64|Base64 encoding/decoding]]

A-55. [[contributed-scripts#^SEDAPPEND|Inserting text in a file using _sed_]]

A-56. [[contributed-scripts#^GRONSFELD|The Gronsfeld Cipher]]

A-57. [[contributed-scripts#^BINGO|Bingo Number Generator]]

A-58. [[contributed-scripts#^BASICSREVIEWED|Basics Reviewed]]

A-59. [[contributed-scripts#^TESTEXECTIME|Testing execution times of various commands]]

A-60. [[contributed-scripts#^ASSOCARRTEST|Associative arrays vs. conventional arrays (execution times)]]

C-1. [[C.2. Awk#^LETTERCOUNT2|Counting Letter Occurrences]]

J-1. [[tabexpansion#^USEGETOPTEX|Completion script for _UseGetOpt.sh_]]

M-1. [[sample-bashrc#^BASHRC|Sample .bashrc file]]

M-2. [[sample-bashrc#^BASHPROF|.bash_profile file]]

N-1. [[Appendix N. Converting DOS Batch Files to Shell Scripts#^VIEWDAT|VIEWDATA.BAT: DOS Batch File]]

N-2. [[Appendix N. Converting DOS Batch Files to Shell Scripts#^VIEWDATA|_viewdata.sh_: Shell Script Conversion of VIEWDATA.BAT]]

T-1. [[Appendix T. ASCII Table#^ASCIISH|A script that generates an ASCII table]]

T-2. [[Appendix T. ASCII Table#^ASCII2SH|Another ASCII table script]]

T-3. [[Appendix T. ASCII Table#^ASCII3SH|A third ASCII table script, using _awk_]]
