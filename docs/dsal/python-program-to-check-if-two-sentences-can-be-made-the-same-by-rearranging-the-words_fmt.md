# Python 程序通过重新排列单词来检查两个句子是否可以相同

> 原文: [https://www.geeksforgeeks.org/python-program-to-check-if-two-sentences-can-be-made-the-same-by-rearranging-the-words/](https://www.geeksforgeeks.org/python-program-to-check-if-two-sentences-can-be-made-the-same-by-rearranging-the-words/)

给定代表两个句子的两个字符串 `S1` 和 `S2`，任务是检查是否可以通过重新排列任何一个字符串的单词来使两个句子相同。

**示例:**

> **输入:** `S1 = "please select a category"`, `S2 = "category a please select"`
> **输出:** Yes
>
> **输入:** `S1 = "hello world this is python language"`, `S2 = "python language is this modern world"`
> **输出:** No
> **解释:** 第二个字符串中不存在“hello”这个词。

### 方法一：使用 `sort()` 和 `split()` 内置函数

按照步骤解决问题:

*   将字符串 `S1` 和 `S2` 的单词分别存储在单独的列表中，比如 `list1[]` 和 `list2[]`。
*   按升序对两个列表进行排序。
*   如果发现两个列表相等，打印 `"Yes"`。否则，打印 `"No"`。

以下是上述方法的实现:

## Python 3

```python
# Python implementation
# of the above approach

# Function to check if two sentences
# can be made same by rearranging words
def ReArrangeStrings(string1, string2):

    # Stores the words of the
    # sentences in separate lists
    list1 = list(string1.split())
    list2 = list(string2.split())

    # Sort both the strings
    list1.sort()
    list2.sort()

    # If two lists are equal
    if(list1 == list2):
        return True
    else:
        return False

# Driver Code

# Input
S1 = "please select a category"
S2 = "category please a select"

# Function call to check if two sentences
# can be made same by rearranging words
if(ReArrangeStrings(S1, S2)):
    print("Yes")
else:
    print("No")
```

### Output:

```
Yes
```

**时间复杂度:** `O(N* M* log(N))`，其中 `M` 是最长字符串的长度。
**辅助空间:** `O(N)`

### 方法二：使用 `Counter()` 和 `split()` 内置函数

按照步骤解决问题:

*   将字符串 `S1` 和 `S2` 的单词分别存储在单独的列表中，比如 `list1[]` 和 `list2[]`。
*   使用 `Counter()` 函数计算字符串 `S1` 和 `S2` 中出现的单词，并将其存储在单独的变量中，分别表示 `counter1` 和 `counter2`。
*   检查 `counter1` 是否等于 `counter2`。如果发现是真的，打印 `"Yes"`。否则，打印 `"No"`。

以下是上述方法的实现:

## Python 3

```python
# Python implementation
# of the above approach

# Import counter function
# from collections
from collections import Counter

# Function to check if two sentences
# can be made same by rearranging words
def ReArrange(S1, S2):

    # Store the words of the
    # strings in separate lists
    list1 = list(S1.split())
    list2 = list(S2.split())

    listcounter1 = Counter(list1)
    listcounter2 = Counter(list2)

    # If counter of both the
    # sentences are same
    if(listcounter1 == listcounter2):
        return True
    else:
        return False

# Driver Code

# Input
S1 = "please select a category"
S2 = "category please a select"

# Function call to check if two
# sentences can be made same
# by rearranging words
if(ReArrange(S1, S2)):
    print("Yes")
else:
    print("No")
```

### Output:

```
Yes
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(N)`