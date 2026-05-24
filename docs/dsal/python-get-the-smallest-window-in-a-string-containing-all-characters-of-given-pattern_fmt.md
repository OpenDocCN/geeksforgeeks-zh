# Python | 获取包含给定模式所有字符的字符串中最小的窗口

> 原文: [https://www.geeksforgeeks.org/python-get-the-smallest-window-in-a-string-containing-all-characters-of-given-pattern/](https://www.geeksforgeeks.org/python-get-the-smallest-window-in-a-string-containing-all-characters-of-given-pattern/)

给定两个字符串 `str` 和 `pattern`，在包含模式所有字符的 `str` 中找到最小的子字符串。

## 示例:

```
Input : str = 'geeksforgeeks' pattern = 'gks' 
Output : geeks

Input : str = 'new string' pattern = 'rg' 
Output : ring
```

## 方法#1 : 使用 Python `enumerate()`

此方法使用 Python `enumerate()`。`need[k]` 存储我们需要多少次字符 `k` 而 `missing` 则告诉我们还有多少字符缺失。在循环中，首先将新字符添加到窗口中。然后，如果没有遗漏任何内容，尽可能从窗口开始处删除，然后更新结果。

```
string = 'new string'
pattern = 'rg'

# let's find the index of r and g in String and the
# stor them in index list (index[]) 
index=[]
for x in range(len(pattern)):
    if pattern[x] in string:
        index.append(string.index(pattern[x]))

# sorting the r and g index's
index.sort()

# save first index in l
l = len(index)
low = int(index[0])

# save  last index in h
high = int(index[l-1])
h = high +1
for i in range(low,h):
    print(string[i],end=" ")
```

**Output:**

```
ksf
```