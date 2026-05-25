# Python 中的 Regex，在以大写字母开头的单词之间放置空格

> 原文: [https://www.geeksforgeeks.org/regex-in-python-to-put-spaces-between-words-starting-with-capital-letters/](https://www.geeksforgeeks.org/regex-in-python-to-put-spaces-between-words-starting-with-capital-letters/)

给定一组字符，基本上就是一个句子。然而，不同的单词之间没有空格，每个单词的第一个字母都是大写的。您需要在以下修改后打印这句话:

1.  在这些单词之间留出一个空格。
2.  将大写字母转换为小写字母。

**示例:**

```
Input : BruceWayneIsBatman
Output : bruce wayne is batman

Input :  GeeksForGeeks
Output :  geeks for geeks
```

这个问题我们已经有了解决方案，请参考[在以大写字母开头的单词之间放空格](https://www.geeksforgeeks.org/put-spaces-words-starting-capital-letters/)链接。

我们可以使用 [re (regex) 库](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)的 [`findall()`](https://www.geeksforgeeks.org/regular-expressions-python-set-1-search-match-find/) 方法在 python 中快速解决这个问题。

**思路:**

1.  使用 `re.findall(expression, str)` 方法拆分每个以大写字母开头的单词。
2.  现在将每个单词的大写字母改为小写，并用空格连接每个单词。

## Python 3

```python
import re

def putSpace(input):
    # regex [A-Z][a-z]* means any string starting
    # with capital character followed by many
    # lowercase letters
    words = re.findall('[A-Z][a-z]*', input)

    # Change first letter of each word into lower case
    for i in range(0, len(words)):
        words[i] = words[i][0].lower() + words[i][1:]
    print(' '.join(words))

# Driver program
if __name__ == "__main__":
    input = 'BruceWayneIsBatman'
    putSpace(input)
```

**输出:**

```
bruce wayne is batman
```