# Python–unittest 中的 `assertLessEqual()` 函数

> 原文: [https://www.geeksforgeeks.org/python-assertlessequal-function-in-unittest/](https://www.geeksforgeeks.org/python-assertlessequal-function-in-unittest/)

Python 中的 `assertLessEqual()` 是一个 `unittest` 库函数，用于单元测试中检查第一个给定值是否小于或等于第二个值。该函数将采用三个参数作为输入，并根据断言条件返回一个布尔值。

此函数检查第一个给定值是否小于或等于第二个值，如果小于或等于第二个值，则返回 `True`，否则如果第一个值不小于或等于第二个值，则返回 `False`。

> **语法**: `assertLessEqual(first, second, msg=None)`
>
> **参数**: `assertLessEqual()` 接受以下列出的三个参数，并进行解释:
>
> *   **first**: 第一个输入值（整数）
> *   **second**: 第二个输入值（整数）
> *   **msg**: 作为测试用例失败时显示的消息的字符串。

下面列出了一个示例，说明了给定断言函数的正测试用例和负测试用例:

### 示例 1

```py
# test suite
import unittest

class TestStringMethods(unittest.TestCase):

    # negative test function to test if value1 is less or equal than value2
    def test_negativeForLessEqual(self):
        first = 6
        second = 5

        # error message in case if test case got failed
        message = "first value is not less than or equal to second value."

        # assert function() to check if value1 is less or equal than value2
        self.assertLessEqual(first, second, message)

if __name__ == '__main__':
    unittest.main()
```

**输出:**

> F
> ======================================================================
> FAIL: test_negativeForLessEqual (__main__.TestStringMethods)
> ----------------------------------------------------------------------
> Traceback (most recent call last):
>   File "p1.py", line 13, in test_negativeForLessEqual
>     self.assertLessEqual(first, second, message)
> AssertionError: 6 is not less than or equal to 5 : first value is not less than or equal to second value.
>
> ----------------------------------------------------------------------
> Ran 1 test in 0.000s
>
> FAILED (failures=1)

### 示例 2

```py
# test suite
import unittest

class TestStringMethods(unittest.TestCase):

    # positive test function to test if value1 is less or equal than value2
    def test_positiveForLessEqual(self):
        first = 4
        second = 4

        # error message in case if test case got failed
        message = "first value is not less than or equal to second value."

        # assert function() to check if value1 is less or equal than value2
        self.assertLessEqual(first, second, message)

if __name__ == '__main__':
    unittest.main()
```

**输出:**

> .
> ----------------------------------------------------------------------
> Ran 1 test in 0.000s
>
> OK