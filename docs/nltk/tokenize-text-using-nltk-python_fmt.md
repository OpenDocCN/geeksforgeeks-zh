# 使用 Python 中的 NLTK 标记文本

> 原文：[https://www.geeksforgeeks.org/tokenize-text-using-nltk-python/](https://www.geeksforgeeks.org/tokenize-text-using-nltk-python/)

要运行下面的 Python 程序，必须在您的系统中安装（NLTK）自然语言工具包。
NLTK 模块是一个庞大的工具包，旨在帮助您掌握整个自然语言处理（NLP）方法。
要安装 NLTK，请在您的终端中运行以下命令。

*   `sudo pip install nltk`
*   然后，只需在终端中输入 `python` 即可进入 Python shell
*   键入 `import nltk`
*   `nltk.download('all')`

由于需要下载大量的标记器、分块器、其他算法和所有的语料库，上述安装将花费相当长的时间。

*   **语料库** – 正文，单数。语料库是这个的复数。
*   **词汇** – 单词及其含义。
*   **Token** – Each “entity” that is a part of whatever was split up based on rules. For examples, each word is a token when a sentence is “tokenized” into words. Each sentence can also be a token, if you tokenized the sentences out of a paragraph.

**所以基本上标记化包括从正文中拆分句子和单词。**

```python
# import the existing word and sentence tokenizing
# libraries
from nltk.tokenize import sent_tokenize, word_tokenize

text = "Natural language processing (NLP) is a field " + \
       "of computer science, artificial intelligence " + \
       "and computational linguistics concerned with " + \
       "the interactions between computers and human " + \
       "(natural) languages, and, in particular, " + \
       "concerned with programming computers to " + \
       "fruitfully process large natural language " + \
       "corpora. Challenges in natural language " + \
       "processing frequently involve natural " + \
       "language understanding, natural language" + \
       "generation frequently from formal, machine" + \
       "-readable logical forms), connecting language " + \
       "and machine perception, managing human-" + \
       "computer dialog systems, or some combination " + \
       "thereof."

print(sent_tokenize(text))
print(word_tokenize(text))
```

**OUTPUT**

*   ['Natural language processing (NLP) is a field of computer science, artificial intelligence and computational linguistics concerned with the interactions between computers and human (natural) languages, and, in particular, concerned with programming computers to fruitfully process large natural language corpora.', 'Challenges in natural language processing frequently involve natural language understanding, natural language generation (frequently from formal, machine-readable logical forms), connecting language and machine perception, managing human-computer dialog systems, or some combination thereof.']
*   ['Natural', 'language', 'processing', '(', 'NLP', ')', 'is', 'a', 'field', 'of', 'computer', 'science', ',', 'artificial', 'intelligence', 'and', 'computational', 'linguistics', 'concerned', 'with', 'the', 'interactions', 'between', 'computers', 'and', 'human', '(', 'natural', ')', 'languages', ',', 'and', ',', 'in', 'particular', ',', 'concerned', 'with', 'programming', 'computers', 'to', 'fruitfully', 'process', 'large', 'natural', 'language', 'corpora', '.', 'Challenges', 'in', 'natural', 'language', 'processing', 'frequently', 'involve', 'natural', 'language', 'understanding', ',', 'natural', 'language', 'generation', '(', 'frequently', 'from', 'formal', ',', 'machine-readable', 'logical', 'forms', ')', ',', 'connecting', 'language', 'and', 'machine', 'perception', ',', 'managing', 'human-computer', 'dialog', 'systems', ',', 'or', 'some', 'combination', 'thereof', '.']

在那里，我们创建了标记，最初是句子，后来是单词。

本文由 **Pratima Upadhyay** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。