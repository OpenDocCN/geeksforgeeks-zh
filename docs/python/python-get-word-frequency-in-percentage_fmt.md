# Python–获取词频百分比

> 原文: [https://www.geeksforgeeks.org/python-get-word-frequency-in-percentage/](https://www.geeksforgeeks.org/python-get-word-frequency-in-percentage/)

给定一个字符串列表，任务是编写一个 Python 程序来获取字符串列表中每个单词的百分比份额。

## 计算解释

(X 字出现次数/总字数) * 100。

## 示例

**输入:**
`test_list = ["Gfg is best for geeks", "All love Gfg", "Gfg is best for CS", "For CS geeks Gfg is best"]`

**输出:**
`{'Gfg': 0.21052631578947367, 'is': 0.15789473684210525, 'best': 0.15789473684210525, 'for': 0.10526315789473684, 'geeks': 0.10526315789473684, 'All': 0.05263157894736842, 'love': 0.05263157894736842, 'CS': 0.10526315789473684}`

**解释:** 每个单词相对于列表中所有其他单词的频率百分比。`Gfg` 出现 4 次。总字数 = 19。

**输入:**
`test_list = ["Gfg is best for geeks", "All love Gfg"]`

**输出:**
`{'Gfg': 0.25, 'is': 0.125, 'best': 0.125, 'for': 0.125, 'geeks': 0.125, 'All': 0.125, 'love': 0.125}`

**解释:** 每个单词相对于列表中所有其他单词的频率百分比。

## 方法#1: 使用 `sum()` + `Counter()` + `join()` + `split()`

在本例中，我们使用 `join()` 连接每个字符串后，使用 `split()` 来获取每个单词。`Counter()` 获取每个单词映射的频率。最后使用 `sum()` 计算所有单词的总数，以获得每个单词所需的份额，利用存储在 `Counter` 中的频率。

```py
# Python3 code to demonstrate working of
# Each word frequency percentage
# Using sum() + Counter()+ join() + split()
from collections import Counter

# initializing list
test_list = ["Gfg is best for geeks",
             "All love Gfg", 
             "Gfg is best for CS",
             "For CS geeks Gfg is best"]

# printing original list
print("The original list is : " + str(test_list))

# concatenating using join 
joined = " ".join(ele for ele in test_list)

# mapping using Counter()
mappd = Counter(joined.split())

# getting total using sum 
total_val = sum(mappd.values())

# getting share of each word
res = {key: val / total_val for key,
       val in mappd.items()}

# printing result
print("Percentage share of each word : " + str(res))
```

**输出:**

> 原列表为: ['Gfg is best for geeks', 'All love Gfg', 'Gfg is best for CS', 'For CS geeks Gfg is best']
> 每个单词所占的百分比份额: {'Gfg': 0.21052631578947367, 'is': 0.15789473684210525, 'best': 0.15789473684210525, 'for': 0.10526315789473684, 'geeks': 0.10526315789473684, 'All': 0.05263157894736842, 'love': 0.05263157894736842, 'CS': 0.10526315789473684}

## 方法2: 使用组合单行表达式

与上述方法类似，只是将每个片段组合起来，以提供紧凑的单行解决方案。

```py
# Python3 code to demonstrate working of
# Each word frequency percentage
# Using combined one-liner 
from collections import Counter

# initializing list
test_list = ["Gfg is best for geeks", "All love Gfg", 
            "Gfg is best for CS", "For CS geeks Gfg is best"]

# printing original list
print("The original list is : " + str(test_list))

# mapping using Counter()
mappd = Counter(" ".join(ele for ele in test_list).split())

# getting share of each word
res = {key: val / sum(mappd.values()) for key,
       val in mappd.items()}

# printing result
print("Percentage share of each word : " + str(res))
```

**输出:**

> 原列表为: ['Gfg is best for geeks', 'All love Gfg', 'Gfg is best for CS', 'For CS geeks Gfg is best']
> 每个单词所占的百分比份额: {'Gfg': 0.21052631578947367, 'is': 0.15789473684210525, 'best': 0.15789473684210525, 'for': 0.10526315789473684, 'geeks': 0.10526315789473684, 'All': 0.05263157894736842, 'love': 0.05263157894736842, 'CS': 0.10526315789473684}