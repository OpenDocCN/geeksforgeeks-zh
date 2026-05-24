# Python–使用附魔

## 找到 Levenshtein 距离

> 原文: [https://www.geeksforgeeks.org/python-find-the-levenshtein-distance-using-enchant/](https://www.geeksforgeeks.org/python-find-the-levenshtein-distance-using-enchant/)

[两个字符串之间的 Levenshtein 距离](https://en.wikipedia.org/wiki/Levenshtein_distance)定义为在给定字符串 1 中插入、删除或替换以将其转换为另一个字符串 2 所需的最小字符数。

**示例:**

> **输入:** `string1 = "geek"`, `string2 = "gesek"`
> **输出:** 1
> **说明:** 我们可以通过插入一个's'将 `string1` 转换成 `string2`。
>
> **输入:** `string1 = "cat"`, `string2 = "cut"`
> **输出:** 1
> **说明:** 我们可以通过将'a'替换为'u'来将 `string1` 转换为 `string2`。
>
> **输入:** `string1 = "sunday"`, `string2 = "saturday"`
> **输出:** 3
> **说明:** 后三个和前一个字符相同。我们基本上需要把"un"转换成"atur"。这可以通过以下三种操作来完成。将"n"替换为"r"，插入 t，插入 a。

使用 `enchant` 模块的 `enchant.utils.levenshtein()` 方法可以找到两个字符串之间的 Levenshtein 距离。

### `enchant.utils.levenshtein()`

> **语法:** `enchant.utils.levenshtein(string1, string2)`
>
> **参数:**
> `string1`: 要比较的第一个字符串
> `string2`: 要比较的第二个字符串
>
> **返回:** 一个表示 Levenshtein 距离的整数

**Example 1:**

```py
# import the enchant module
import enchant

# determining the values of the parameters
string1 = "abc"
string2 = "aef"

# the Levenshtein distance between
# string1 and string2
print(enchant.utils.levenshtein(string1, string2))
```

**输出:**

```py
2
```

**例 2:**

```py
# import the enchant module
import enchant

# determining the values of the parameters
string1 = "Hello World"
string2 = "Hello d"

# the Levenshtein distance between
# string1 and string2
print(enchant.utils.levenshtein(string1, string2))
```

**输出:**

```py
6
```

**例 3:**

```py
# import the enchant module
import enchant

# determining the values of the parameters
string1 = "Computer Science Portal"
string2 = "Computer Portal"

# the Levenshtein distance between
# string1 and string2
print(enchant.utils.levenshtein(string1, string2))
```

**输出:**

```py
9
```