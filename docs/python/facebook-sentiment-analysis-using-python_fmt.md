# 使用 Python 进行情感分析

> 原文：[https://www.geeksforgeeks.org/facebook-sentiment-analysis-using-python/](https://www.geeksforgeeks.org/facebook-sentiment-analysis-using-python/)

本文是一篇使用 VADER 进行的 Facebook 情感分析。如今许多政府机构和公司需要了解客户对 Facebook 等社交媒体的反馈和评论。

![](img/f2420e2e6aa52777789f3b1e620188f0.png)

## 什么是情感分析？

情感分析是机器学习最好的现代分支之一，主要用于分析数据以了解自己的想法。如今它被许多公司用来从客户那里获得自己的反馈。

## 为什么要用情感分析？

*   **无价营销：**
    利用情感分析，公司和产品拥有者可以了解他们产品的需求和供应情况。
*   **识别关键情绪触发因素：**
    在心理学和其他医疗机构中，情感分析可以用来检测个体的情绪是正常还是异常，并基于数据记录来决定人的健康。
*   **政治：**
    在政治领域，待选候选人可以用情感分析来预测自己的政治地位，衡量人们的接受程度。它还可以用来预测选举委员会的选举结果。
*   **教育：**
    大学和其他像学院这样的高等院校可以利用情感分析来了解学生的反馈和评论，因此可以考虑修改或改进他们的教育课程。

## Anaconda 的设施

*   **NLTK：** 用于理解人类自然语言。
    安装使用 `conda` 命令。
    ```py
    conda install -c anaconda nltk
    ```
*   使用 `pip` 安装。
    ```py
    pip install nltk
    ```
*   **NumPy：** 是 Python 中用于科学和计算方法的包。
    安装使用 `conda`。
    ```py
    conda install -c conda-forge numpy
    ```
*   利用 `pip`。
    ```py
    pip install numpy
    ```
*   **Pandas：** 是一个用于数据预处理和分析的 Python 模块。
    使用 `conda` 安装。
    ```py
    conda install -c anaconda pandas
    ```
*   使用 `pip` 安装。
    ```py
    pip install pandas
    ```
*   **Matplotlib：** 是一个 Python 模块，用于数据可视化和数据表示的 2D 绘图。
    安装使用 `conda`。
    ```py
    conda install -c conda-forge matplotlib
    ```
*   使用 `pip` 安装。
    ```py
    pip install matplotlib
    ```

## 数据获取

获取 Facebook 评论的方法有很多，这些方法是：
*   Facebook Graph API
*   直接从 Facebook 下载
*   从另一个数据集提供商网站下载

在上述方法中，我们使用了从最好的数据集提供商 Kaggle 网站下载 Facebook 评论数据集。对于我们已经使用的代码，分析了 Kindle 亚马逊 Facebook 评论（`kindle.txt`），您可以使用您自己的 Facebook 评论，使用该代码来分析您自己的评论，或者创建一个文本格式的文件，并尝试简化。

下面是实现。

## Python 3 代码

```py
import time
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import nltk
import io
import unicodedata
import numpy as np
import re
import string
from numpy import linalg
from nltk.sentiment.vader import SentimentIntensityAnalyzer
from nltk.tokenize import sent_tokenize, word_tokenize
from nltk.tokenize import PunktSentenceTokenizer
from nltk.tokenize import PunktSentenceTokenizer
from nltk.corpus import webtext
from nltk.stem.porter import PorterStemmer
from nltk.stem.wordnet import WordNetLemmatizer

with open('kindle.txt', encoding ='ISO-8859-2') as f:
    text = f.read()

sent_tokenizer = PunktSentenceTokenizer(text)
sents = sent_tokenizer.tokenize(text)

print(word_tokenize(text))
print(sent_tokenize(text))

porter_stemmer = PorterStemmer()

nltk_tokens = nltk.word_tokenize(text)

for w in nltk_tokens:
    print ("Actual: % s Stem: % s" % (w, porter_stemmer.stem(w)))

wordnet_lemmatizer = WordNetLemmatizer()
nltk_tokens = nltk.word_tokenize(text)

for w in nltk_tokens:
    print ("Actual: % s Lemma: % s" % (w, wordnet_lemmatizer.lemmatize(w)))

text = nltk.word_tokenize(text)
print(nltk.pos_tag(text))

sid = SentimentIntensityAnalyzer()
tokenizer = nltk.data.load('tokenizers / punkt / english.pickle')

with open('kindle.txt', encoding ='ISO-8859-2') as f:
    for text in f.read().split('\n'):
        print(text)
        scores = sid.polarity_scores(text)
        for key in sorted(scores):
            print('{0}: {1}, '.format(key, scores[key]), end ='')

    print()
```

**输出：**

```py
here is the  sample output of the code:
['i', 'love', 'my', 'kindle']
['i love my kindle']
Actual: i Stem: i
Actual: love Stem: love
Actual: my Stem: my
Actual: kindle Stem: kindl
Actual: i Lemma: i
Actual: love Lemma: love
Actual: my Lemma: my
Actual: kindle Lemma: kindle
[('i', 'NN'), ('love', 'VBP'), ('my', 'PRP$'), ('kindle', 'NN')]
i love my kindle
compound: 0.6369, neg: 0.0, neu: 0.323, pos: 0.677,
```

**我们在程序中遵循以下主要步骤：**

*   从 Kaggle 网站下载（获取）Facebook 评论，并将其保存为文本格式。
*   通过 SkLearn 和 `nltk` 库对数据进行预处理。我们首先对数据进行标记化，然后在标记化之后进行词干化和词形还原。
*   使用 VADER 库解析评论。将每条评论分为正面、负面或中性。

**现在，让我们试着理解上面这段代码：**

*   首先，我们打开一个名为 `kindle` 的文件，它是从 Kaggle 网站下载的，并保存在本地磁盘中。
    > `with open('kindle.txt', encoding='ISO-8859-2') as f:`
*   打开一个文件后，我们通过 `tokenize`、`stemize` 和 `lemmatize` 对文本进行预处理：
    *   标记文本，即从文本中拆分单词。
        > `sent_tokenizer = PunktSentenceTokenizer(text)`
        > `sents = sent_tokenizer.tokenize(text)`
        > `print(word_tokenize(text))`
        > `print(sent_tokenize(text))`
*   对文本进行词干化和词形还原，以便对文本进行规范化：
    1) 对于词干化，我们使用 `PorterStemmer()` 函数：
        > `from nltk.stem.porter import PorterStemmer`
        > `porter_stemmer = PorterStemmer()`
        > `nltk_tokens = nltk.word_tokenize(text)`
        > `for w in nltk_tokens:`
        > `print("Actual: % s Stem: % s" % (w, porter_stemmer.stem(w)))`
    2) 对于词形还原，我们使用 `WordNetLemmatizer()` 函数：
        > `from nltk.stem.wordnet import WordNetLemmatizer`
        > `wordnet_lemmatizer = WordNetLemmatizer()`
        > `nltk_tokens = nltk.word_tokenize(text)`
        > `for w in nltk_tokens:`
        > `print("Actual: % s Lemma: % s" % (w, wordnet_lemmatizer.lemmatize(w)))`
*   标记标记，只选择重要的特征/标记，如形容词、副词和动词等。
    ```py
    text = nltk.word_tokenize(text)
    print(nltk.pos_tag(text))
    ```
*   将标记传递给情感强度分析器，该分析器将 Facebook 评论分为正面、负面或中性。

**以下是 VADER 情感分析器的工作原理：**

*   VADER 使用了“情感词典”的组合，这是一个词汇特征（例如单词）的列表，通常根据它们的语义方向将其标记为积极或消极。
*   情感分析器不仅告诉我们积极和消极的分数，还告诉我们情绪有多积极或消极。
*   然后，我们使用 `polarity_scores()` 方法获得给定句子的极性索引。
    然后，我们将评论强度和极性构建为：
    > `sid = SentimentIntensityAnalyzer()`
    > `tokenizer = nltk.data.load('tokenizers/punkt/english.pickle')`
    > `with open('kindle.txt', encoding='ISO-8859-2') as f:`
    > `for text in f.read().split('\n'):`
    > `print(text)`
    > `scores = sid.polarity_scores(text)`
    > `for key in sorted(scores):`
    > `print('{0}: {1}, '.format(key, scores[key]), end='')`
    > `print()`
*   让我们来了解什么是情感代码，以及 VADER 如何处理上述代码的输出：
    ```py
     i love my kindle
    compound: 0.6369, neg: 0.0, neu: 0.323, pos: 0.677
    ```
*   阳性（`pos`）、阴性（`neg`）和中性（`neu`）分数代表属于这些类别的文本比例。这意味着我们的句子被评为 67% 积极，32% 中立和 0% 消极。因此所有这些加起来应该是 1。
*   复合评分（`compound`）是一种度量标准，用于计算在 -1（极端负值）和 +1（极端正值）之间标准化的所有词典评分的总和。
*   最后，返回评论的情感分数。