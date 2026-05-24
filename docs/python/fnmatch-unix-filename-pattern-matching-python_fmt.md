# fnmatch–Python 中的 Unix 文件名模式匹配

> 原文：[https://www.geeksforgeeks.org/fnmatch-unix-filename-pattern-matching-python/](https://www.geeksforgeeks.org/fnmatch-unix-filename-pattern-matching-python/)

该模块用于匹配 Unix shell 风格的通配符。`fnmatch()`将单个文件名与模式进行比较，如果它们匹配，则返回 `TRUE`，否则返回 `FALSE`。
当操作系统使用区分大小写的文件系统时，比较区分大小写。
壳式通配符中使用的特殊字符及其功能有：

*   `*` – 匹配所有内容
*   `?` – 匹配任何单个字符
*   `[序列]` – 匹配序列中的任何字符
*   `[!seq]` – 匹配任何不在 `seq` 中的字符

元字符应该用括号括起来，以便进行文字匹配。例如，`[?]` 匹配字符 `?`。

## fnmatch 模块提供的功能

### 1. `fnmatch.fnmatch(filename, pattern)`

此函数测试给定的 `filename` 字符串是否与 `pattern` 字符串匹配，并返回一个布尔值。如果操作系统不区分大小写，则在执行比较之前，两个参数都将被规范化为全小写或全大写。

**示例：** 搜索所有以 `fnmatch` 开头，以 `.py` 结尾的文件的脚本。

```py
# Python program to illustrate 
# fnmatch.fnmatch(filename, pattern) 
import fnmatch 
import os

pattern = 'fnmatch_*.py'
print ('Pattern :', pattern )
print()

files = os.listdir('.') 
for name in files: 
    print ('Filename: %-25s %s' % (name, fnmatch.fnmatch(name, pattern)))
```

**输出：**

```py
$ python fnmatch_fnmatch.py

Pattern : fnmatch_*.py

Filename: __init__.py               False
Filename: fnmatch_filter.py         True
Filename: fnmatch_fnmatch.py        True
Filename: fnmatch_fnmatchcase.py    True
Filename: fnmatch_translate.py      True
Filename: index.rst                 False
```

### 2. `fnmatch.fnmatchcase(filename, pattern)`

此函数执行区分大小写的比较，测试给定的 `filename` 字符串是否与 `pattern` 字符串匹配，并返回一个布尔值。

**示例：** 不考虑文件系统和操作系统设置，编写区分大小写的比较脚本。

```py
# Python program to illustrate 
# fnmatch.fnmatchcase(filename, pattern) 
import fnmatch 
import os

pattern = 'FNMATCH_*.PY'
print ('Pattern :', pattern) 
print()

files = os.listdir('.')

for name in files: 
    print ('Filename: %-25s %s' % (name, fnmatch.fnmatchcase(name, pattern)))
```

**输出：**

```py
$ python fnmatch_fnmatchcase.py

Pattern : FNMATCH_*.PY

Filename: __init__.py               False
Filename: fnmatch_filter.py         False
Filename: FNMATCH_FNMATCH.PY        True
Filename: fnmatch_fnmatchcase.py    False
Filename: fnmatch_translate.py      False
Filename: index.rst                 False
```

### 3. `fnmatch.filter(names, pattern)`

此函数返回传入函数的 `names` 列表中匹配给定 `pattern` 的子集。

**示例：** 按多个文件扩展名过滤文件。

```py
# Python program to illustrate 
# fnmatch.filter(names, pattern) 
import fnmatch 
import os

pattern = 'fnmatch_*.py'
print ('Pattern :', pattern )

files = os.listdir('.') 
print ('Files :', files)

print ('Matches :', fnmatch.filter(files, pattern))
```

**输出：**

```py
$ python fnmatch_filter.py

Pattern : fnmatch_*.py
Files   : ['__init__.py', 'fnmatch_filter.py', 'fnmatch_fnmatch.py', 
'fnmatch_fnmatchcase.py', 'fnmatch_translate.py', 'index.rst']
Matches : ['fnmatch_filter.py', 'fnmatch_fnmatch.py',
'fnmatch_fnmatchcase.py', 'fnmatch_translate.py']
```

### 4. `fnmatch.translate(pattern)`

此函数将 shell 风格的 `pattern` 转换为正则表达式，以便与 `re.match()` 一起使用（`re.match()` 只会在字符串的开头匹配，而不是在每一行的开头匹配）。

```py
# Python program to illustrate 
# fnmatch.translate(pattern) 
import fnmatch, re

regex = fnmatch.translate('*.txt') 
reobj = re.compile(regex)

print(regex) 
print(reobj.match('foobar.txt')) 
```

**输出：**

```py
'(?s:.*\\.txt)\\Z'
_sre.SRE_Match object; span=(0, 10), match='foobar.txt'
```

本文由 **阿迪提·古普塔** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。