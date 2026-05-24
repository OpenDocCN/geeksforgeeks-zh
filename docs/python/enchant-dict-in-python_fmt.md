# Enchant. Python 中的 Dict()

> 原文: [https://www.geeksforgeeks.org/enchant-dict-in-python/](https://www.geeksforgeeks.org/enchant-dict-in-python/)

`Enchant` 是 python 中的一个模块，用于检查单词的拼写，给出纠正单词的建议。同时，给出了单词的反义词和同义词。它检查字典中是否有一个单词。

## enchant.Dict()

`enchant.Dict()` 是 `enchant` 模块的内置方法。用于创建 Dict 对象，这是 `enchant` 模块中最重要的对象。Dict 对象代表特定语言的字典。

> **语法:** `enchant.Dict(tag)`
>
> **参数:**
> `tag`: 语言词典的代码(可选)
>
> **返回:** 一个字典对象

## 例 1 :

```py
# import the enchant module
import enchant

# dictionary of en_US
d = enchant.Dict("en_US")

# the dictionary tag
tag = d.tag
print("The dictionary tag is " + tag)
```

```
The dictionary tag is en_US
```

## 例 2 :

当执行 `enchant.Dict()` 方法时，不传递任何参数，默认取本地机器语言的代码。

```py
# import the enchant module
import enchant

# instantiating the dictionary
# without passing any parameter
d = enchant.Dict()

# finding the dictionary tag
tag = d.tag
print("The dictionary tag is " + tag)
```

```
The dictionary tag is en_IN
```

## 示例 3 :

如果没有合适的字典，则 `enchant.Dict()` 方法可能会失败。在这种情况下，将打印以下消息:

```py
enchant.Dict()
```

**输出:**

> Traceback (most recent call last):
>   File "<stdin>", line 1, in <module>
>   File "C:\Users\user\AppData\Local\Programs\Python\Python37-32\lib\site-packages\enchant\__init__.py", line 541, in __init__
>     _EnchantObject.__init__(self)
>   File "C:\Users\user\AppData\Local\Programs\Python\Python37-32\lib\site-packages\enchant\__init__.py", line 144, in __init__
>     self._init_this()
>   File "C:\Users\user\AppData\Local\Programs\Python\Python37-32\lib\site-packages\enchant\__init__.py", line 548, in _init_this
>     this = self._broker._request_dict_data(self.tag)
>   File "C:\Users\user\AppData\Local\Programs\Python\Python37-32\lib\site-packages\enchant\__init__.py", line 286, in _request_dict_data
>     self._raise_error(e_str % (tag,), DictNotFoundError)
>   File "C:\Users\user\AppData\Local\Programs\Python\Python37-32\lib\site-packages\enchant\__init__.py", line 233, in _raise_error
>     raise eclass(default)
> enchant.errors.DictNotFoundError: No dictionary for language 'English_India'