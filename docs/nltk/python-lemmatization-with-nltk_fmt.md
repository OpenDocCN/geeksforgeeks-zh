# Python：用 NLTK 进行词形还原

> 原文：[https://www.geeksforgeeks.org/python-lemmatization-with-nltk/](https://www.geeksforgeeks.org/python-lemmatization-with-nltk/)

词形还原是将一个单词的不同屈折形式组合在一起的过程，这样它们就可以作为一个单独的项目进行分析。词形还原类似于词干提取，但它给词带来了语境。所以它把意思相似的词和一个词联系起来。
文本预处理包括[词干提取](https://www.geeksforgeeks.org/introduction-to-stemming/)和词形还原。很多时候，人们发现这两个术语令人困惑。有些人把这两个当作一回事。实际上，词形还原比词干提取更受欢迎，因为词形还原可以对单词进行形态学分析。
词形还原的应用有：

*   用于搜索引擎等综合检索系统。
*   用于紧凑索引。

```text
Examples of lemmatization:

-> rocks : rock
-> corpora : corpus
-> better : good
```

词干提取的一个主要区别是，词形还原采用了一个词性参数`pos`，如果不提供，默认为“名词”。
下面是使用 NLTK 的词形还原词的实现：

## Python 3

```python
# import these modules
from nltk.stem import WordNetLemmatizer

lemmatizer = WordNetLemmatizer()

print("rocks :", lemmatizer.lemmatize("rocks"))
print("corpora :", lemmatizer.lemmatize("corpora"))

# a denotes adjective in `pos`
print("better :", lemmatizer.lemmatize("better", pos ="a"))
```

**输出：**

```python
rocks : rock
corpora : corpus
better : good
```