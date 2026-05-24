# Python–unittest 中的 `assertGreater()` 函数

> 原文: [https://www.geeksforgeeks.org/python-assertgreater-function-in-unittest/](https://www.geeksforgeeks.org/python-assertgreater-function-in-unittest/)

Python 中的 `assertGreater()` 是一个 `unittest` 库函数，在单元测试中用来检查第一个给定值是否大于第二个给定值。该函数将采用三个参数作为输入，并根据断言条件返回一个布尔值。

该函数检查第一个给定值是否大于第二个给定值，如果大于则返回真，否则如果第一个给定值不大于第二个给定值则返回假。

> **语法:** `assertGreater(first, second, msg=None)`
>
> **参数:** `assertGreater()` 接受下面列出的三个参数，并给出解释:
>
> *   `first`: 第一个输入值（整数）
> *   `second`: 第二个输入值（整数）
> *   `msg`: 作为测试用例失败时显示的消息的字符串。

下面列出了一个示例，说明了给定断言函数的正测试用例和负测试用例:

## 例 1

```py
# test suite
import unittest

class TestStringMethods(unittest.TestCase):

    # negative test function to test if value1
    # is greater than value2
    def test_negativeForGreater(self):
        first = 4
        second = 5

        # error message in case if test case got failed
        message = "first value is not greater that second value."

        # assert function() to check if value1 is
        # greater than value2
        self.assertGreater(first, second, message)

if __name__ == '__main__':
    unittest.main()
```

**输出:**

> F
> ======================================================================
> FAIL: test_negativeForGreater (__main__.TestStringMethods)
> ----------------------------------------------------------------------
> Traceback (most recent call last):
>   File "p1.py", line 13, in test_negativeForGreater
>     self.assertGreater(first, second, message)
> AssertionError: 4 not greater than 5 : first value is not greater that second value.
>
> ----------------------------------------------------------------------
> Ran 1 test in 0.000s
>
> FAILED (failures=1)

## 例 2

```py
# test suite
import unittest

class TestStringMethods(unittest.TestCase):

    # positive test function to test if values
    # are almost equal with place
    def test_positiveForGreater(self):
        first = 4
        second = 3

        # error message in case if test case got failed
        message = "first value is not greater that second value."

        # assert function() to check if value1 is
        # greater than value2
        self.assertGreater(first, second, message)

if __name__ == '__main__':
    unittest.main()
```

**输出:**

> .
> ----------------------------------------------------------------------
> Ran 1 test in 0.000s
>
> OK