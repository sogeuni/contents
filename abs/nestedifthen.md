# 7.4. Nested _if/then_ Condition Tests

Condition tests using the _if/then_ construct may be nested. The net result is equivalent to using the [_&&_](ops.html#LOGOPS1) compound comparison operator.

|   |
|---|
|a=3

if [ "$a" -gt 0 ]
then
  if [ "$a" -lt 5 ]
  then
    echo "The value of \"a\" lies somewhere between 0 and 5."
  fi
fi

# Same result as:

if [ "$a" -gt 0 ] && [ "$a" -lt 5 ]
then
  echo "The value of \"a\" lies somewhere between 0 and 5."
fi|

[[37.1. Bash, version 2#^CARDS|Example 37-4]] and [Example 17-11](system.html#BACKLIGHT) demonstrate nested _if/then_ condition tests.
