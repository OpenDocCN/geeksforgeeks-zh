# Python unittest中的assertGreaterEqual()函数

> 原文: [https://www.geeksforgeeks.org/python-assertgreaterequal-function-in-unittest/](https://www.geeksforgeeks.org/python-assertgreaterequal-function-in-unittest/)

`assertGreaterEqual()`是**unittest**库中的一个函数，用于单元测试中检查第一个给定值是否大于等于第二个值。该函数将采用三个参数作为输入，并根据断言条件返回一个布尔值。

该函数检查第一个给定值是否大于或等于第二个值，如果大于或等于第二个值，则返回真，否则返回假。

> **语法:** `assertGreaterEqual(first, second, msg=None)`
>
> **参数:** `assertGreaterEqual()`接受以下列出的三个参数:
>
> *   `first`: 第一个输入值（整数）
> *   `second`: 第二个输入值（整数）
> *   `msg`: 作为测试用例失败时显示的消息的字符串。

下面列出了一个示例，说明了给定断言函数的正测试用例和负测试用例:

**示例:**

## Python 3

```py
# test suite
import unittest

class TestStringMethods(unittest.TestCase):

    # negative test function to test if value1 is greater or equal than value2
    def test_negativeForGreaterEqual(self):
        first = 4
        second = 5

        # error message in case if test case got failed
        message = "first value is not greater or equal than second value."

        # assert function() to check if value1 is greater or equal than value2
        self.assertGreaterEqual(first, second, message)

if __name__ == '__main__':
    unittest.main()
```

**输出:**

> F
> ======================================================================
> FAIL: test_negativeForGreaterEqual (__main__.TestStringMethods)
> ----------------------------------------------------------------------
> Traceback (most recent call last):
>   File "p1.py", line 13, in test_negativeForGreaterEqual
>     self.assertGreaterEqual(first, second, message)
> AssertionError: 4 is not greater than or equal to 5 : first value is not greater or equal than second value.
>
> ----------------------------------------------------------------------
> Ran 1 test in 0.000s
>
> FAILED (failures=1)

**例 2:**

## Python

```py
# test suite
import unittest

class TestStringMethods(unittest.TestCase):

    # positive test function to test if value1 is greater than or equal to value2
    def test_positiveForGreaterEqual(self):
        first = 4
        second = 4

        # error message in case if test case got failed
        message = "first value is not greater or equal than second value."

        # assert function() to check if value1 is greater or equal than value2
        self.assertGreaterEqual(first, second, message)

if __name__ == '__main__':
    unittest.main()
```

**输出:**

> .
> ----------------------------------------------------------------------
> Ran 1 test in 0.000s
>
> OK