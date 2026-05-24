# Python 字典，设置并计数检查频率是否可以相同

> 原文: [https://www.geeksforgeeks.org/python-dictionary-set-counter-check-frequencies-can-become/](https://www.geeksforgeeks.org/python-dictionary-set-counter-check-frequencies-can-become/)

给定一个包含较低字母字符的字符串，我们需要从该字符串中最多删除一个字符，这样字符串中每个不同字符的频率就变得相同。

## 示例

```py
Input  : str = “xyyz”
Output : Yes
We can remove character ’y’ from above 
string to make the frequency of each 
character same.

Input : str = “xyyzz” 
Output : Yes
We can remove character ‘x’ from above 
string to make the frequency of each 
character same.

Input : str = “xxxxyyzz” 
Output : No
It is not possible to make frequency of 
each character same just by removing at 
most one character from above string.
```

## 解决方案

此问题已有解决方案，请参考[检查一次移除](https://www.geeksforgeeks.org/check-if-frequency-of-all-characters-can-become-same-by-one-removal/)链接是否可以使所有字符的频率变得相同。我们将在 Python 中快速解决这个问题。方法很简单：

1.  我们需要统计字符串中每个字母的频率，为此我们将使用 [`Counter(input)`](https://www.geeksforgeeks.org/counters-in-python-set-1/) 方法，它返回一个以字符为键，以它们各自的频率为值的字典。
2.  现在提取每个字符的频率列表，并在 Python 中的 [`Set()`](https://www.geeksforgeeks.org/sets-in-python/) 数据结构中推送这些值。
3.  由于集合包含唯一值，因此如果集合大小为 1，则意味着所有字符的频率都相同；如果大小为 2，则检查第一个元素的值是否为 1（如果为 1，则可以通过最多删除一个字符来使频率相同，否则不可能）。

## 代码实现

```py
# Function to Check if frequency of all characters
# can become same by one removal
from collections import Counter

def allSame(input):
    # calculate frequency of each character
    # and convert string into dictionary
    dict = Counter(input)

    # now get list of all values and push it
    # in set
    same = list(set(dict.values()))

    if len(same) > 2:
        print('No')
    elif len(same) == 2 and same[1] - same[0] > 1:
        print('No')
    else:
        print('Yes')

# now check if frequency of all characters 
# can become same

# Driver program
if __name__ == "__main__":
    input = 'xxxyyzzt'
    allSame(input)
```

## 输出

```py
No
```