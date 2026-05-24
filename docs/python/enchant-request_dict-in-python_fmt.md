# Python 中的 `enchant.request_dict()`

> 原文: [https://www.geeksforgeeks.org/enchant-request_dict-in-python/](https://www.geeksforgeeks.org/enchant-request_dict-in-python/)

`Enchant` 是 Python 中的一个模块，用于检查单词的拼写，给出纠正单词的建议。同时，给出了单词的反义词和同义词。它检查字典中是否有一个单词。

## `enchant.request_dict()`

`enchant.request_dict()` 是 `enchant` 模块的内置方法。它用于获取特定语言的字典对象。

> **语法:** `enchant.request_dict(tag)`
>
> **参数:**
> `tag`: 语言代码
>
> **返回:** 一个字典对象

**例 1 :**

```py
# import the enchant module
import enchant

# dictionary of en_US
d = enchant.request_dict("en_US")

# the dictionary tag
tag = d.tag
print("The dictionary tag is " + tag)
```

```
The dictionary tag is en_US
```

**例 2 :** 当执行 `enchant.request_dict()` 方法时，不传递任何参数，默认取本地机器语言的代码。

```py
# import the enchant module
import enchant

# instantiating the dictionary
# without passing any parameter
d = enchant.request_dict()

# finding the dictionary tag
tag = d.tag
print("The dictionary tag is " + tag)
```

```
The dictionary tag is en_IN
```

**示例 3 :** 如果没有合适的字典，则 `enchant.request_dict()` 方法可能会失败。在这种情况下，将打印以下消息:

```py
enchant.request_dict()
```

**输出:**

> Traceback (most recent call last):
>   File "<stdin>", line 1, in <module>
>   File "C:\Users\user\AppData\Local\Programs\Python\Python37-32\lib\site-packages\enchant\__init__.py", line 272, in request_dict
>     return Dict(tag, self)
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
> enchant.enchant.errors.DictNotFoundError: No dictionary found for language 'English_India'