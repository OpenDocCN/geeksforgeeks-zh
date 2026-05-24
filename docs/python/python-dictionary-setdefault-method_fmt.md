# Python 字典 setdefault() 方法

> 原文: [https://www.geeksforgeeks.org/python-dictionary-setdefault-method/](https://www.geeksforgeeks.org/python-dictionary-setdefault-method/)

Python 中的字典是一个无序的数据值集合，用于像映射一样存储数据值。与其他只保存单个值作为元素的数据类型不同，字典保存 `key : value` 对。

在 Python 字典中，`setdefault()` 方法返回键对应的值（如果键在字典中）。如果没有，它会将带有该值的键插入字典。

> **语法:** `dict.setdefault(key, default_value)`
> **参数:** 需要两个参数:
> **Key –** 在字典中搜索的键。
> **default_value (可选) –** 如果键不在字典中，则值为 `default_value` 的键会插入到字典中。如果未提供，默认值将为 `None`。
> **返回:**
> 键在字典中的值。
> 如果键不在字典中且未指定 `default_value`，则为 `None`。
> 如果键不在字典中并且指定了 `default_value`，则为 `default_value`。

**例 1:**

```py
# Python program to show working
# of setdefault() method in Dictionary

# Dictionary with single item
Dictionary1 = { 'A': 'Geeks', 'B': 'For', 'C': 'Geeks'}

# using setdefault() method
Third_value = Dictionary1.setdefault('C')
print("Dictionary:", Dictionary1)
print("Third_value:", Third_value)
```

**输出:**

```py
Dictionary: {'A': 'Geeks', 'C': 'Geeks', 'B': 'For'}
Third_value: Geeks
```

**例 2:** 当键不在字典里时。

```py
# Python program to show working
# of setdefault() method in Dictionary

# Dictionary with single item
Dictionary1 = { 'A': 'Geeks', 'B': 'For'}

# using setdefault() method
# when key is not in the Dictionary
Third_value = Dictionary1.setdefault('C')
print("Dictionary:", Dictionary1)
print("Third_value:", Third_value)

# using setdefault() method
# when key is not in the Dictionary
# but default value is provided
Fourth_value = Dictionary1.setdefault('D', 'Geeks')
print("Dictionary:", Dictionary1)
print("Fourth_value:", Fourth_value)
```

**输出:**

```py
Dictionary: {'A': 'Geeks', 'B': 'For', 'C': None}
Third_value: None
Dictionary: {'A': 'Geeks', 'B': 'For', 'C': None, 'D': 'Geeks'}
Fourth_value: Geeks
```