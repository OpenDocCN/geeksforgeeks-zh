# Python | NLTK ConditionalFreqDist()

> 原文: [https://www.geeksforgeeks.org/python-nltk-nltk-tokenize-conditionalfreqdist/](https://www.geeksforgeeks.org/python-nltk-nltk-tokenize-conditionalfreqdist/)

借助`nltk.tokenize.ConditionalFreqDist()`方法，我们可以统计一个句子中单词的出现频率。

## 语法
`tokenize.ConditionalFreqDist()`

## 返回
返回字典中单词的频率分布。

## 例 1
在这个例子中我们可以看到，通过使用`tokenize.ConditionalFreqDist()`方法，我们能够统计一个句子中单词的出现次数。

```py
# import ConditionalFreqDist() method from nltk
from nltk.probability import ConditionalFreqDist
from nltk.tokenize import word_tokenize

# Create a reference variable for Class SExprTokenizer
tk = ConditionalFreqDist()

# Create a string input
gfg = "Geeks for Geeks"

for word in word_tokenize(gfg):
   condition = len(word)
   tk[condition][word] += 1

print(tk)
```

**输出:**
> FreqDist({"Geeks": 2, "for": 1})

## 例 2

```py
# import ConditionalFreqDist() method from nltk
from nltk.probability import ConditionalFreqDist
from nltk.tokenize import word_tokenize

# Create a reference variable for Class SExprTokenizer
tk = ConditionalFreqDist()

# Create a string input
gfg = "G F G"

for word in word_tokenize(gfg):
   condition = len(word)
   tk[condition][word] += 1

print(tk)
```

**输出:**
> FreqDist({'G': 2, 'F': 1})