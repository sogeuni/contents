---
title: 7.4. Nested _if/then_ Condition Tests
---

Condition tests using the _if/then_ construct may be nested. The net result is equivalent to using the [[operators#LOGOPS1|_&&_]] compound comparison operator.

```bash
a=3

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
fi
```

[[bash-ver2#^CARDS|Example 37-4]] and [[system-and-administrative-commands#BACKLIGHT|Example 17-11]] demonstrate nested _if/then_ condition tests.
