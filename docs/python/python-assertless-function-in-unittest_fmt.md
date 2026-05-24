# Python unittest 中的 assertLess() 函数

> 原文: [https://www.geeksforgeeks.org/python-assertless-function-in-unittest/](https://www.geeksforgeeks.org/python-assertless-function-in-unittest/)

Python 中的 `assertLess()` 是一个 [unittest](https://www.geeksforgeeks.org/unit-testing-python-unittest/) 库函数，用于单元测试中检查第一个给定值是否小于第二个给定值。该函数将采用三个参数作为输入，并根据断言条件返回一个布尔值。

该函数检查第一个给定值是否小于第二个给定值，如果小于，则返回真，否则如果第一个给定值不小于第二个给定值，则返回假。

> **语法:** `assertLess(first, second, msg=None)`
>
> **参数:** `assertLess()` 接受以下列出的三个参数，并进行解释:
>
> *   `first`: 第一个输入值（整数）
> *   `second`: 第二个输入值（整数）
> *   `msg`: 作为测试用例失败时显示的消息的字符串。

下面列出了一个示例，说明了给定断言函数的正测试用例和负测试用例:

## 例 1: 如果第一个值不小于第二个值

```py
# test suite
import unittest

class TestStringMethods(unittest.TestCase):

    # negative test function to test if
    # values1 is less than value2
    def test_negativeForLess(self):
        first = 6
        second = 5

        # error message in case if test case got failed
        message = "first value is not less that second value."

        # assert function() to check if values1 is
        # less than value2
        self.assertLess(first, second, message)

# main for function call
if __name__ == '__main__':
    unittest.main()
```

**输出:**

```
F
======================================================================
FAIL: test_negativeForLess (__main__.TestStringMethods)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "p1.py", line 13, in test_negativeForLess
    self.assertLess(first, second, message)
AssertionError: 6 is not less than 5: first value is not less that second value.

----------------------------------------------------------------------
Ran 1 test in 0.000s

FAILED (failures=1)
```

## 例 2: 如果第一给定值小于第二给定值

```py
# test suite
import unittest

class TestStringMethods(unittest.TestCase):

    # positive test function to test if
    # values are almost equal with place
    def test_positiveForLess(self):
        first = 2
        second = 3

        # error message in case if test case got failed
        message = "first value is not less that second value."

        # assert function() to check if values1 is
        # less than value2
        self.assertLess(first, second, message)

# main for function call
if __name__ == '__main__':
    unittest.main()
```

**输出:**

```
.
----------------------------------------------------------------------
Ran 1 test in 0.000s

OK
```