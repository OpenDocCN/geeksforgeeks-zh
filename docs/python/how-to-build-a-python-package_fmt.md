# 如何构建 Python 包？

> 原文：[https://www.geeksforgeeks.org/how-to-build-a-python-package/](https://www.geeksforgeeks.org/how-to-build-a-python-package/)

在本文中，我们将学习如何用 Python 开发包。包只不过是为执行某一组任务而设计的程序的集合。包有两种类型，即

*   内置包，如 `set`、`datetime`、`sqlite` 等。
*   外部包，如 `flask`、`django`、`tensorflow` 等。

## 创建包

首先，我们需要想办法构造我们的代码，这样其他人就可以访问我们的代码功能。在 Python 中，要制作一个包，我们需要向目录中添加一个 `__init__.py` 文件。在这里，我们将制作一个名为 `test_package` 的包。

*   让我们编写 `__init__.py` 文件。

```py
from collections import Counter

def count_in_list(l, word):
  c = Counter(l)
  return c[word]
```

*   现在，创建一个名为 `test_package` 的目录，并将 `__init__.py` 文件放入其中。这样，我们的包就准备好了。我们这个包的功能是计算一个单词在列表中出现的次数。现在，要使用我们的包，请在 `test_package` 目录外创建一个 `run.py` 文件。在 `run.py` 中，只需导入新创建的包并使用 `count_in_list` 函数。我们可以编写如下代码。

```py
from test_package import count_in_list

l = ["gfg", "dsa", "gfg"]
count = count_in_list(l, "gfg")
print(count)
```