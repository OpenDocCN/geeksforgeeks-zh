# 使用更好的脏话审查 Python 中的脏话

> 原文: [https://www.geeksforgeeks.org/censor-bad-words-in-python-using-better-profanity/](https://www.geeksforgeeks.org/censor-bad-words-in-python-using-better-profanity/)

在本文中，我们将学习如何使用 Python 审查不良单词。为此，我们使用 Python 中的 `better_profanit`y 模块。

## 安装

```py
pip install better_profanity
```

对于审查脏话，我们使用的是来自 `better_profanity` 的 `profanity.censor()` 方法。所以，我们先讨论它的语法和参数。

> **语法:** `profanity.censor(text, censor_char='*')`
>
> **参数:**
>
> `text`: 待审查文本
>
> `censor_char`: `'*'` 默认情况下，字符要审查不良文字
>
> **返回值:** 审查文本

## 进场

1.  导入包 (`better_profanit`y)
2.  声明或输入要审查的文本。
3.  使用 `profanity.censor()` 方法，获得审查的文本。
4.  打印经过审查的文本。

## 例 1

```py
# importing package
from better_profanity import profanity

# text to be censored
text = "What the shit are you doing?"

# do censoring
censored = profanity.censor(text)

# view output
print(censored)
```

**输出:**

```py
What the **** are you doing?
```

## 例 2

```py
# importing package
from better_profanity import profanity

# text to be censored
text = "What the shit are you doing?"

# do censoring
censored = profanity.censor(text, '$')

# view output
print(censored)
```

**输出:**

```py
What the $$ are you doing?
```