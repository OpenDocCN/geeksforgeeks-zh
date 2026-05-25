# Python 中的 Zip 函数，改为新的字符集

> 原文: [https://www.geeksforgeeks.org/zip-function-python-change-new-character-set/](https://www.geeksforgeeks.org/zip-function-python-change-new-character-set/)

给定一个 26 个字母的字符集，它相当于英语字母表的字符集（即 ABCD……xyz）并充当关系。我们还会得到几个句子，我们必须在给定的新字符集的帮助下翻译它们。

## 示例

```
New character set : qwertyuiopasdfghjklzxcvbnm
Input : "utta"
Output : geek

Input : "egrt"
Output : code
```

对于这个问题我们已经有了解决方案，请参考[将字符串更改为新的字符集](https://www.geeksforgeeks.org/change-string-to-a-new-character-set/)链接。我们将使用 [`Zip()`](https://www.geeksforgeeks.org/using-iterations-in-python-effectively/) 方法和[字典](https://www.youtube.com/watch?v=z7z_e5-l2yE&t=31s)数据结构在 python 中解决这个问题。方法很简单：

## 解决方案

1.  创建一个字典数据结构，我们将把原始的英语字符集映射到新给定的字符集。`zip(charSet, origCharSet)` 已经为我们完成了这项工作。它将原始字符集的每个字符序列映射到新字符集的每个给定字符，并返回一个元组对的列表。现在我们使用 `dict()` 将其转换为字典。
2.  遍历原始字符串并将其转换为新的字符串。

## 代码实现

```python
# Function to change string to a new character
def newString(charSet, input):
    # map original character set of english
    # onto new character set given
    origCharSet = 'abcdefghijklmnopqrstuvwxyz'
    mapChars = dict(zip(charSet, origCharSet))

    # iterate through original string and get
    # characters of original character set
    changeChars = [mapChars[chr] for chr in input]

    # join characters without space to get new string
    print(''.join(changeChars))

# Driver program
if __name__ == "__main__":
    charSet = 'qwertyuiopasdfghjklzxcvbnm'
    input = 'utta'
    newString(charSet, input)
```

## 输出

```
geek
```