# 如何用 Python 生成随机电话号码？

> 原文：[https://www.geeksforgeeks.org/how-to-generate-a-random-phone-number-using-python/](https://www.geeksforgeeks.org/how-to-generate-a-random-phone-number-using-python/)

在本文中，我们将学习如何使用 Python 生成随机电话号码。一般来说，印度的电话号码是 10 位数，以 9、8、7 或 6 开头。

## 进场：

*   我们将使用 `random` 库来生成随机数。
*   数字应包含 10 位。
*   如果第一位数字以 9、8、7 或 6 开头，我们将使用 [`randint()`](https://www.geeksforgeeks.org/python-randint-function/) 方法。
*   剩余的 9 位数字也将由 [`randint()`](https://www.geeksforgeeks.org/python-randint-function/) 方法生成。

## 例：

```py
The generated random phone numbers would looklike:
```

## 实现：

### 蟒 3

```py
# import module
import random as r

ph_no = []

# the first number should be in the range of 6 to 9
ph_no.append(r.randint(6, 9))

# the for loop is used to append the other 9 numbers.
# the other 9 numbers can be in the range of 0 to 9.
for i in range(1, 10):
    ph_no.append(r.randint(0, 9))

# printing the number
for i in ph_no:
    print(i, end="")
```

## 输出：

```py

```