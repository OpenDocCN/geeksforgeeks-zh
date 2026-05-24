# Python groupby 方法删除所有连续的重复项

> 原文: [https://www.geeksforgeeks.org/python-groupby-method-remove-consecutive-duplicates/](https://www.geeksforgeeks.org/python-groupby-method-remove-consecutive-duplicates/)

给定一个字符串，删除所有连续的重复项。

## 示例

```
Input  : aaaaabbbbbb
Output : ab

Input : geeksforgeeks
Output : geksforgeks

Input : aabccba
Output : abcba
```

这个问题我们已经有了解决方案，请参考[从字符串中删除所有连续的重复项](https://www.geeksforgeeks.org/remove-consecutive-duplicates-string/)。我们可以使用 [`itertools.groupby()`](https://docs.python.org/3/library/itertools.html#itertools.groupby) 方法在 Python 中快速解决这个问题。

## `itertools.groupby(iterable, key=None)` 在 Python 中是如何工作的？

`groupby` 方法接受两个输入：一个是**可迭代对象**（列表、元组、字典），第二个是计算可迭代中每个元素的键的键函数。它返回分组项的关键字和可重复项。如果键函数未指定或为 `None`，则键默认为标识函数，并返回元素不变。例如，

```
numbers = [1, 1, 1, 3, 3, 2, 2, 2, 1, 1]
import itertools
for (key, group) in itertools.groupby(numbers):
    print(key, list(group))
```

输出:

```
(1, [1, 1, 1])
(3, [3, 3])
(2, [2, 2])
(1, [1, 1])
```

```
# function to remove all consecutive duplicates
# from the string in Python

from itertools import groupby
def removeAllConsecutive(input):

    # group all consecutive characters based on their
    # order in string and we are only concerned
    # about first character of each consecutive substring
    # in given string, so key value will work for us
    # and we will join these keys without space to
    # generate resultant string
    result = []
    for (key, group) in groupby(input):
        result.append(key)

    print(''.join(result))

# Driver program
if __name__ == "__main__":
    input = 'aaaaabbbbbb'
    removeAllConsecutive(input)
```

输出:

```
ab
```

## 参考文献

[https://docs.python.org/3/library/itertools.html](https://docs.python.org/3/library/itertools.html)