# Python程序统计字典中的偶数和奇数

> 原文：[https://www.geeksforgeeks.org/python-program-to-count-even-and-odd-numbers-in-a-dictionary/](https://www.geeksforgeeks.org/python-program-to-count-even-and-odd-numbers-in-a-dictionary/)

给定一个[python字典](https://www.geeksforgeeks.org/python-dictionary/)，任务是计算字典中出现的偶数和奇数。

示例：

> 输入：`{'a': 1, 'b': 2, 'c': 3, 'd': 4, 'e': 5}`
> 输出：偶数= 2，奇数= 3
>
> 输入：`{'x': 4, 'y': 9, 'z': 16}`
> 输出：偶数= 2，奇数= 1

## 方法一：使用 `values()` 函数

使用 [`values()`](https://www.geeksforgeeks.org/python-dictionary-values/) 函数遍历字典并提取其元素，对于每个提取的值，[检查它是偶数还是奇数](https://www.geeksforgeeks.org/check-whether-given-number-even-odd/)。最后，打印相应的计数。

```python
# Python3 Program to count even and
# odd numbers present in a dictionary

# Function to count even and odd
# numbers present in a dictionary
def countEvenOdd(dict):

    # Stores count of even
    # and odd elements
    even = 0
    odd = 0

    # Traverse the dictionary
    for i in dict.values():

        if i % 2 == 0:
            even = even + 1
        else:
            odd = odd + 1

    print("Even Count: ", even)
    print("Odd Count: ", odd)

# Driver Code
dict = {'a': 1, 'b': 2, 'c': 3, 'd': 4, 'e': 5}
countEvenOdd(dict)
```

输出：

```
Even Count:  2
Odd Count:  3
```

时间复杂度：`O(N)`
辅助空间：`O(1)`

## 方法二：迭代字典项

[迭代字典中的每一项](https://www.geeksforgeeks.org/iterate-over-a-dictionary-in-python/)，对于每个元素，检查它是偶数还是奇数。最后，打印相应的计数。

```python
# Python3 Program to count even
# and odd elements in a dictionary

# Function to count even and
# odd elements in a dictionary
def countEvenOdd(dict):
    even = 0
    odd = 0

    # Iterate over the dictionary
    for i in dict:

        # If current element is even
        if dict[i] % 2 == 0:

            # Increase count of even
            even = even + 1

        # Otherwise
        else:

            # Increase count of odd
            odd = odd + 1

    print("Even count: ", even)
    print("Odd count: ", odd)

# Driver Code
# Given Dictionary
dict = {'a': 1, 'b': 2, 'c': 3, 'd': 4, 'e': 5}

countEvenOdd(dict)
```

输出：

```
Even count:  2
Odd count:  3
```

时间复杂度：`O(N)`
辅助空间：`O(1)`