# Python 中的数据类 | 集合 4 (继承)

> 原文: [https://www.geeksforgeeks.org/data-classes-in-python-set-4-inheritance/](https://www.geeksforgeeks.org/data-classes-in-python-set-4-inheritance/)

先决条件: [Python 中的继承](https://www.geeksforgeeks.org/inheritance-in-python/)、[Python 中的数据类 | 集合 3](https://www.geeksforgeeks.org/data-classes-in-python-set-3-dataclass-fields/)

## 概述

在这篇文章中，我们将讨论继承时数据类的行为。尽管数据类有自己的构造函数，但它们的行为与普通类继承时的行为非常相似。

## 示例代码

```py
from dataclasses import dataclass

@dataclass
class Article:
    title: str
    content: str
    author: str

@dataclass
class GfgArticle(Article):
    language: str
    author: str
    upvotes: int = 0
```

上述代码的几点:

1.  `Article` 由 `GfgArticle` 子类化。
2.  超类和子类都是数据类 - 尽管超类或子类也可能是普通类。当数据类继承普通类时，超类的 `__init__()` 在子类中被覆盖。
3.  `GfgArticle` 中的 `author` 覆盖了 `Article` 中的相同内容 - 作为继承的基本概念，其赋值首先在子类中查找，然后在超类中查找树。

## `GfgArticle.__init__()` 的行为

*   如果 `__init__()` 没有显式提供，默认的 `__init__()` 期望超类 (`Article`) 的属性，后跟子类的属性作为参数。

    > `GfgArticle(title: str, content: str, author: str, language: str, upvotes: int = 0)`

**注:** 签名期望 `author` 在 `language` 之前 - 尽管 `GfgArticle` 中的声明顺序相反。这是因为属性是从超类到子类从上到下扫描的。所以 `author` 首先在 `Article` 中扫描，然后 `language` 在 `GfgArticle` 中扫描。

### 示例代码

```py
dClassObj = GfgArticle("DataClass",
                       "SuperCool DataStructure",
                       "vibhu4agarwal",
                       "Python3")
print(dClassObj)
```

### 输出

```
GfgArticle(title='DataClass', content='SuperCool DataStructure', author='vibhu4agarwal', language='Python3', upvotes=0)
```

*   如果 `__init__()` 被显式提供，它应该以某种方式初始化它自己的所有属性以及超类 (`Article`) 中的属性。

### 示例代码

```py
from dataclasses import dataclass

@dataclass
class Article:
    title: str
    content: str
    author: str

@dataclass(init = False)
class GfgArticle(Article):
    language: str
    author: str
    upvotes: int = 0

    def __init__(self, title):
        self.title = title
        self.language = "Python3"
        self.author = "vibhu4agarwal"
        self.content = "Inheritance Concepts"

dClassObj = GfgArticle("DataClass")
print(dClassObj)
```

### 输出

```
GfgArticle(title='DataClass', content='Inheritance Concepts', author='vibhu4agarwal', language='Python3', upvotes=0)
```

**注:**

*   `__init__()` 中的参数要求可以根据需要进行调整，只要它有一些初始化所有属性的方法。
*   初始化的顺序无关紧要。`language` 在 `author` 之前初始化，而 `content` 终于初始化了，还能用。