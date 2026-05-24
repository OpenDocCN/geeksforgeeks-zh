# Python |从列表中查找输入字符串的所有相近匹配项

> 原文: [https://www.geeksforgeeks.org/python-find-close-matches-input-string-list/](https://www.geeksforgeeks.org/python-find-close-matches-input-string-list/)

我们得到了一个模式字符串列表和一个输入字符串。我们需要在模式字符串列表中找到所有可能的足够好的输入字符串匹配。

示例:

```py
Input : patterns = ['ape', 'apple', 
                  'peach', 'puppy'], 
          input = 'appel'
Output : ['apple', 'ape']
```

我们可以使用内置函数`difflib.get_close_matches()`在python中快速解决这个问题。

### `difflib.get_close_matches()`函数在Python中是如何工作的？

`difflib.get_close_matches(word, possibilities, n, cutoff)`接受四个参数，其中`n`、`cutoff`可选。`word`是期望紧密匹配的序列，`possibilities`是匹配单词的序列列表。可选参数`n`（默认为3）是要返回的最大相近匹配数，`n`必须大于0。可选参数`cutoff`（默认为0.6）是[0，1]范围内的一个浮点数。得分至少和`word`不太相似的可能性被忽略。
`possibilities`中的最佳（不超过`n`个）匹配在列表中返回，按相似性得分排序，最相似的优先。

```py
# Function to find all close matches of 
# input string in given list of possible strings
from difflib import get_close_matches

def closeMatches(patterns, word):
     print(get_close_matches(word, patterns))

# Driver program
if __name__ == "__main__":
    word = 'appel'
    patterns = ['ape', 'apple', 'peach', 'puppy']
    closeMatches(patterns, word)
```

**参考文献:** [https://docs.python.org/2/library/difflib.html](https://docs.python.org/2/library/difflib.html)

输出:

```py
['apple', 'ape']
```