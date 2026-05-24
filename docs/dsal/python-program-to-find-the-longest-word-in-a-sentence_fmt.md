# Python 程序查找句子中最长的单词

> 原文: [https://www.geeksforgeeks.org/python-program-to-find-the-longest-word-in-a-sentence/](https://www.geeksforgeeks.org/python-program-to-find-the-longest-word-in-a-sentence/)

给定一个由小写英文字母组成的字符串 `S`，任务是用 python 打印给定字符串中最长的单词。

**示例:**

> **输入:** `S = "be confident and be yourself"`
> **输出:** `['confident']`
> **解释:**
> 句中出现的词有“be”、“confident”、“and”、“be”和“yourself”。
> 每个单词的长度分别为 2、9、3、2 和 8。
> 所以，最长的词是“confident”。
>
> **输入:** `S = "geeks for geeks"`
> **输出:** `['geeks']`

## 基于搜索的方法

参考[这篇](https://www.geeksforgeeks.org/program-find-smallest-largest-word-string/)文章，通过执行以下步骤来解决这个问题:

*   迭代字符串的字符。
*   检查当前遇到的字符是空格还是字符串的结尾。
*   如果发现当前字符是这样，则更新获得的最大单词长度。
*   最后，打印使用 `substr()` 方法获得的最长单词。

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`

## 方法使用 `sorted()` 方法

想法是将字符串拆分成单独的单词并存储在列表中。然后，使用 `sorted()` 方法按照长度递增的顺序对列表进行排序。打印排序列表中的最后一个字符串。

下面是上述方法的实现:

### Python 3

```python
# Python3 program for the above approach

# Function to print the longest
# word in given sentence
def largestWord(s):

    # Sort the words in increasing
    # order of their lengths
    s = sorted(s, key = len)

    # Print last word
    print(s[-1])

# Driver Code
if __name__ == "__main__":

    # Given string
    s = "be confident and be yourself"

    # Split the string into words
    l = list(s.split(" "))

    largestWord(l)
```

**Output:**

```
confident
```

**时间复杂度:** `O(N * logN)`
**辅助空间:** `O(1)`