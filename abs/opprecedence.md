# 8.4. Operator Precedence

In a script, operations execute in order of _precedence_: the higher precedence operations execute _before_ the lower precedence ones. [^1]

| Operator | Meaning | Comments |
| :--- | :--- | :--- |
|  |  | **HIGHEST PRECEDENCE** |
| var++ var-- | post-increment, post-decrement | [[assortedtips#^CSTYLE\|C-style]] operators |
| ++var --var | pre-increment, pre-decrement |  |
|  |  |  |
| ! ~ | [negation](special-chars.html#NOTREF) | logical / bitwise, inverts sense of following operator |
|  |  |  |
| ** | [exponentiation](ops.html#EXPONENTIATIONREF) | [arithmetic operation](ops.html#AROPS1) |
| * / % | multiplication, division, modulo | arithmetic operation |
| + - | addition, subtraction | arithmetic operation |
|  |  |  |
| << >> | left, right shift | [bitwise](ops.html#BITWSOPS1) |
|  |  |  |
| -z -n | _unary_ comparison | string is/is-not [null](comparison-ops.html#STRINGNULL) |
| -e -f -t -x, etc. | _unary_ comparison | [file-test](fto.html) |
| < -lt > -gt <= -le >= -ge | _compound_ comparison | string and integer |
| -nt -ot -ef | _compound_ comparison | file-test |
| == -eq [!=](comparison-ops.html#NOTEQUAL) -ne | equality / inequality | test operators, string and integer |
|  |  |  |
| & | AND | bitwise |
| ^ | XOR | _exclusive_ OR, bitwise |
| \| | OR | bitwise |
|  |  |  |
| && -a | AND | [logical](ops.html#LOGOPS1), _compound_ comparison |
| \| -o | OR | logical, _compound_ comparison |
|  |  |  |
| ?: | [trinary operator](special-chars.html#CSTRINARY) | C-style |
| = | [assignment](varassignment.html#EQREF) | (do not confuse with equality _test_) |
| *= /= %= += -= <<= >>= &= | [combination assignment](ops.html#ARITHOPSCOMB) | times-equal, divide-equal, mod-equal, etc. |
|  |  |  |
| , | [comma](ops.html#COMMAOP) | links a sequence of operations |
|  |  | **LOWEST PRECEDENCE** |
**Table 8-1. Operator Precedence** ^1

In practice, all you really need to remember is the following:

- The "My Dear Aunt Sally" mantra (_multiply, divide, add, subtract_) for the familiar [arithmetic operations](ops.html#AROPS1).
    
- The _compound_ logical operators, **&&**, **||**, **-a**, and **-o** have low precedence.
    
- The order of evaluation of equal-precedence operators is usually _left-to-right_.
    

Now, let's utilize our knowledge of operator precedence to analyze a couple of lines from the /etc/init.d/functions file, as found in the _Fedora Core_ Linux distro.

|   |
|---|
|while [ -n "$remaining" -a "$retry" -gt 0 ]; do

# This looks rather daunting at first glance.


# Separate the conditions:
while [ -n "$remaining" -a "$retry" -gt 0 ]; do
#       --condition 1-- ^^ --condition 2-

#  If variable "$remaining" is not zero length
#+      AND (-a)
#+ variable "$retry" is greater-than zero
#+ then
#+ the [ expresion-within-condition-brackets ] returns success (0)
#+ and the while-loop executes an iteration.
#  ==============================================================
#  Evaluate "condition 1" and "condition 2" ***before***
#+ ANDing them. Why? Because the AND (-a) has a lower precedence
#+ than the -n and -gt operators,
#+ and therefore gets evaluated *last*.

#################################################################

if [ -f /etc/sysconfig/i18n -a -z "${NOLOCALE:-}" ] ; then


# Again, separate the conditions:
if [ -f /etc/sysconfig/i18n -a -z "${NOLOCALE:-}" ] ; then
#    --condition 1--------- ^^ --condition 2-----

#  If file "/etc/sysconfig/i18n" exists
#+      AND (-a)
#+ variable $NOLOCALE is zero length
#+ then
#+ the [ test-expresion-within-condition-brackets ] returns success (0)
#+ and the commands following execute.
#
#  As before, the AND (-a) gets evaluated *last*
#+ because it has the lowest precedence of the operators within
#+ the test brackets.
#  ==============================================================
#  Note:
#  ${NOLOCALE:-} is a parameter expansion that seems redundant.
#  But, if $NOLOCALE has not been declared, it gets set to *null*,
#+ in effect declaring it.
#  This makes a difference in some contexts.|

|   |   |
|---|---|
|![[../images/tip.gif|Tip]]|To avoid confusion or error in a complex sequence of test operators, break up the sequence into bracketed sections.

\|   \|
\|---\|
\|if [ "$v1" -gt "$v2"  -o  "$v1" -lt "$v2"  -a  -e "$filename" ]
# Unclear what's going on here...

if [[ "$v1" -gt "$v2" ]] \\| [[ "$v1" -lt "$v2" ]] && [[ -e "$filename" ]]
# Much better -- the condition tests are grouped in logical sections.\||

[^1]: _Precedence_, in this context, has approximately the same meaning as _priority_

