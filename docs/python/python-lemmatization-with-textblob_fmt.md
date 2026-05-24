# Python | 用TextBlob进行词干化

> 原文: [https://www.geeksforgeeks.org/python-lemmatization-with-textblob/](https://www.geeksforgeeks.org/python-lemmatization-with-textblob/)

词干化是将一个单词的不同屈折形式组合在一起的过程，这样它们就可以作为一个单独的项目进行分析。词干化类似于词干提取，但它给词带来了语境。所以它把意思相似的词和一个词联系起来。

文本预处理包括[词干提取](https://www.geeksforgeeks.org/introduction-to-stemming/)和词干化。很多时候，人们发现这两个术语令人困惑。有些人把这两个当作一回事。实际上，词干化比词干提取更受欢迎，因为词干化可以对单词进行形态学分析。

**词干化的应用有:**

*   用于搜索引擎等综合检索系统。
*   用于紧凑索引。

```py
Examples of lemmatization :

-> rocks : rock
-> corpora : corpus
-> better : good
```

词干提取的一个主要区别是，词干化采用了一个词性参数`pos`，如果不提供，默认为“名词”。

下面是使用`TextBlob`实现词干化:

## Python 3

```py
# from textblob lib import Word method
from textblob import Word

# create a Word object.
u = Word("rocks")

# apply lemmatization.
print("rocks :", u.lemmatize())

# create a Word object.
v = Word("corpora")

# apply lemmatization.
print("corpora :", v.lemmatize())

# create a Word object.
w = Word("better")

# apply lemmatization with
# parameter "a", "a" denotes adjective.
print("better :", w.lemmatize("a"))
```

**输出:**

```py
rocks : rock
corpora : corpus
better : good
```