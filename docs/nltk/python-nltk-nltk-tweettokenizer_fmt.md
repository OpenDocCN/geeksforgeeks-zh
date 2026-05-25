# Python NLTK | TweetTokenizer()

## 使用nltk.TweetTokenizer()方法

借助`NLTK nltk.TweetTokenizer()`方法，我们能够将单词流转换成小的标记，以便借助`nltk.TweetTokenizer()`方法分析文本流。

> **语法:** `nltk.TweetTokenizer()`
> **返回:** 返回令牌之流

### 示例 #1

在本例中，当我们以字符串形式传递文本流时，借助`nltk.TweetTokenizer()`方法，它将从一个长字符串转换为小标记。

```py
# import TweetTokenizer() method from nltk
from nltk.tokenize import TweetTokenizer

# Create a reference variable for Class TweetTokenizer
tk = TweetTokenizer()

# Create a string input
gfg = "Geeks for Geeks"

# Use tokenize method
geek = tk.tokenize(gfg)

print(geek)
```

**输出:**

> ['Geeks', 'for', 'Geeks']

### 示例 #2

```py
# import TweetTokenizer() method from nltk
from nltk.tokenize import TweetTokenizer

# Create a reference variable for Class TweetTokenizer
tk = TweetTokenizer()

# Create a string input
gfg = ":-) <> () {} [] :-p"

# Use tokenize method
geek = tk.tokenize(gfg)

print(geek)
```

**输出:**

> [':-)', '<', '>', '(', ')', '{', '}', '[', ']', ':-p']