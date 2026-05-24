# Python 字典（避免错误）

> 原文：[https://www.geeksforgeeks.org/python-dictionary-avoiding-mistakes/](https://www.geeksforgeeks.org/python-dictionary-avoiding-mistakes/)

## 什么是 Python 中的字典？

[Python 字典](https://www.geeksforgeeks.org/python-dictionary/)在类似 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 的语言中类似于哈希表。字典用于在 Python 中创建键值对。可以使用字符串、数字和元组等来代替键。值可以是任何东西。Python 字典用花括号 `{}` 表示。空字典由 `{}` 表示。在 Python 字典中，键和值用 `:` 分隔，键值对用 `,` 分隔。下面的例子解释得很清楚。

## 示例

```py
# program to understand dictionary in python

# creating an empty dictionary
mydictionary ={}

# inserting values in dictionary
mydictionary ={'name':'Ankit',
               'college':'MNNIT',
               'address':'Allahabad'};

# print the dictionary
print(mydictionary)
```

**输出：**

```py
{'address': 'Allahabad', 'name': 'Ankit', 'college': 'MNNIT'}
```

## 使用场景

字典赋予我们模拟各种现实世界应用的能力。我们可以创建一个人的字典，在那里我们可以存储与那个人有关的所有信息，如姓名、年龄、联系地点等。词典中可以存储任何类型的信息，如单词及其含义。Python 字典在机器学习中应用非常广泛，在这种情况下，机器会与人对话，一些预定义的单词被存储为键，它们的含义被存储为值，当用户想要任何东西时，如果找到该东西，就会在键中进行搜索，然后返回其值，否则会显示一些错误。事实上，Python 字典可以用在任何使用普通旧语言的地方。

## 使用字典的示例

```py
# program to understand dictionary in python

# creating an empty dictionary
mydictionary ={}

# inserting values in dictionary
mydictionary ={'greeting':'Hello',
               'status':'how are you',
               'thanks':'thanks visit again'};

# print values according to choice
print(mydictionary['greeting'])
print(mydictionary['status'])
print(mydictionary['thanks'])
```

**输出：**

```py
Hello
how are you
thanks visit again
```

## 使用字典时的常见错误及克服方法

下面是 Python 中使用字典时的一些错误。

### 1. 访问不存在的键

要访问 Python 中字典的元素，请不要直接使用键名访问元素，请始终尝试使用 `.get()` 方法。如果键不存在，则 `.get()` 方法将不打印任何内容，而 `[key]` 将终止整个程序。

```py
# program to understand dictionary in python

# creating an empty dictionary
mydictionary ={}

# inserting values in dictionary
mydictionary ={'greeting':'Hello',
               'status':'how are you',
               'thanks':'thanks visit again'};

# print values according to choice
print(mydictionary['greeting'])
print(mydictionary['status'])
print(mydictionary['thanks'])

# this will print none
print(mydictionary.get('college'))

# this will throw an error
print(mydictionary['college'])
```

**输出：**

```py
Hello
how are you
thanks visit again
None
```

**运行时错误**

```py
Traceback (most recent call last):
  File "/home/ce65dd34285f0cb0781de2a068e658fa.py", line 14, in 
    print(mydictionary['college'])
KeyError: 'college'
```

### 2. 错误地复制字典

当我们想把一本字典复制到另一本字典时，那么应该有正确的复制方法知识。

*   `new_dictionary = old_dictionary`：这一行意味着 `old_dictionary` 和 `new_dictionary` 将引用同一个对象，意味着一个字典中的变化将反映到另一个字典中。
*   `new_dictionary = dict(old_dictionary)` 和 `new_dictionary = old_dictionary.copy()`：将旧词典复制到新词典意味着旧词典中的更新不会反映到新词典中，但新词典中的值将通过使用引用进行复制。这将执行浅层复制。
*   `new_dictionary = copy.deepcopy(old_dictionary)`：这将生成一个深度副本。

```py
# program to understand dictionary in python

# creating an empty dictionary
mydictionary ={}

# inserting values in dictionary
mydictionary ={'greeting':'Hello',
               'status':'how are you',
               'thanks':'thanks visit again'};

# print values according to choice
print(mydictionary['greeting'])
print(mydictionary['status'])
print(mydictionary['thanks'])

# copying dictionary
m = mydictionary
print(m)
```

**输出：**

```py
Hello
how are you
thanks visit again
{'greeting': 'Hello', 'status': 'how are you', 'thanks': 'thanks visit again'}
```

## 什么时候不用字典？

Python 字典在许多情况下都很有用，但是在某些情况下必须避免使用它们。在 Python 中，永远不要认为只有字典是关联数组。总之，我们应该尝试存储相同类型的值。

*   如果我们想搜索值是否出现在字典中，在这种情况下总是使用 Python 集合（`set`），因为在 Python 集合中，无论元素是否出现，都是一个带有布尔值的关联数组。
*   对于固定数量的属性，在 Python 中始终使用类（`class`）或命名元组（`namedtuple`）。
*   当你想要一个预定义的消息时，就使用 `collections.defaultdict`。