# 如何从 Python 中的 NLTK WordNet 获取同义词/反义词？

> 原文：[https://www.geeksforgeeks.org/get-synonymsantonyms-nltk-wordnet-python/](https://www.geeksforgeeks.org/get-synonymsantonyms-nltk-wordnet-python/)

## 简介

WordNet 是一个大型的英语词汇数据库。名词、动词、形容词和副词被组合成一组认知同义词（`synsets`），每一组都表达一个不同的概念。合成集通过概念-语义和词汇关系相互联系。

WordNet 的结构使其成为计算语言学和自然语言处理的有用工具。

WordNet 表面上类似于一个同义词库，因为它根据单词的含义将它们组合在一起。然而，有一些重要的区别。

*   首先，WordNet 不仅链接单词形式——字母串——还链接单词的特定含义。结果，在网络中发现的彼此非常接近的单词在语义上被消除了歧义。
*   其次，WordNet 标注单词之间的语义关系，而词库中的单词分组除了意义相似性之外，不遵循任何明确的模式。

## 获取单词的基本信息

首先，你需要导入 `wordnet`：

```py
from nltk.corpus import wordnet
```

然后，我们可以使用术语 `"program"` 来查找 `synsets`：

```py
syns = wordnet.synsets("program")
```

一个 `synset` 的示例：

```py
print(syns[0].name())
```

仅获取单词：

```py
print(syns[0].lemmas()[0].name())
```

第一个 `synset` 的定义：

```py
print(syns[0].definition())
```

该单词在句子中的使用示例：

```py
print(syns[0].examples())
```

**输出将看起来像：**

```
program.n.01
program
a series of steps to be carried out or goals to be accomplished
['they drew up a six-step program', 'they had plans for a new bond issue']
```

## 获取同义词和反义词

接下来，我们如何辨别一个单词的同义词和反义词？`lemma` 将是同义词，然后你可以使用 `.antonyms()` 找到 `lemma` 的反义词。因此，我们可以填充一些列表：

```py
import nltk
from nltk.corpus import wordnet
synonyms = []
antonyms = []

for syn in wordnet.synsets("good"):
    for l in syn.lemmas():
        synonyms.append(l.name())
        if l.antonyms():
            antonyms.append(l.antonyms()[0].name())

print(set(synonyms))
print(set(antonyms))
```

**输出将是两组同义词和反义词**

```
{'beneficial', 'just', 'upright', 'thorough', 'in_effect', 'good', 'skilled', 'proficient', 'sound', 'unharmed', 'expert', 'adept', 'effective', 'respectable', 'skillful', 'safe', 'commodity', 'honorable', 'right', 'serious', 'mature', 'dear', 'practiced', 'kind', 'secure', 'dependable', 'honest', 'full', 'trade_good'}
{'evil', 'evilness', 'bad', 'badness'}
```

## 对比单词相似度

现在我们来对比任意两个单词的相似度指数：

```py
import nltk
from nltk.corpus import wordnet
# Let's compare the verb of "run" and "sprint"

w1 = wordnet.synset('run.v.01') # v here denotes the tag verb
w2 = wordnet.synset('sprint.v.01')
print(w1.wup_similarity(w2))
```

输出：

```
0.857142857143
```

```py
w1 = wordnet.synset('ship.n.01')
w2 = wordnet.synset('boat.n.01') # n denotes noun
print(w1.wup_similarity(w2))
```

输出：

```
0.9090909090909091
```

---

本文由 **Pratima Upadhyay** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。