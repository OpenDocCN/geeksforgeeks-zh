# 统计 Python 中字符串中唯一字符的数量

> 原文: [https://www.geeksforgeeks.org/count-the-number-of-unique-characters-in-a-string-in-python/](https://www.geeksforgeeks.org/count-the-number-of-unique-characters-in-a-string-in-python/)

给定一个由小写英文字母组成的字符串，任务是找出字符串中存在的唯一字符的数量。

**示例:**

> **输入:** `S = "geeksforgeeks"`
> **输出:** 7
> **解释:** 给定字符串 `"geeksforgeeks"` 包含 7 个唯一字符 `{'g', 'e', 'k', 's', 'f', 'o', 'r'}`。
>
> **输入:** `S = "aaaabbc"`
> **输出:** 3

**方法:** 解决给定问题的思路是在 Python 中初始化一个 `set()`，将给定字符串的所有不同字符存储起来，然后打印集合的大小作为所需答案。

下面是上述方法的实现:

## Python 3

```py
# Python program for the above approach

# Function to count the number of distinct
# characters present in the string str
def countDis(str):

    # Stores all distinct characters
    s = set(str)

    # Return the size of the set
    return len(s)

# Driver Code
if __name__ == "__main__":

    # Given string S
    S = "geeksforgeeks"

    print(countDis(S))
```

**输出:**

```py
7
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`

## 方法二: 使用 `Counter()` 函数

使用 `Counter()` 功能计算所有元素的频率，频率字典的键数给出结果。

下面是实现:

### Python 3

```py
# Python program for the above approach
from collections import Counter

# Function to count the number of distinct
# characters present in the string str
def countDis(str):

    # Stores all frequencies
    freq = Counter(str)

    # Return the size of the freq dictionary
    return len(freq)

# Driver Code
if __name__ == "__main__":

    # Given string S
    S = "geeksforgeeks"

    print(countDis(S))

# This code is contributed by vikkycirus
```

**输出:**

```py
7
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(N)`