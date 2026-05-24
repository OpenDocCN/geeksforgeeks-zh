# 使用 Python 中的 `format()` 格式化容器

> 原文: [https://www.geeksforgeeks.org/formatting-containers-using-format-in-python/](https://www.geeksforgeeks.org/formatting-containers-using-format-in-python/)

让我们看看如何使用 Python 中的 `format()` 方法格式化通过 `__getitem__` 或 `getattr()` 访问的容器。

## 访问支持 `__getitem__` 的容器

### 对于词典

```python
# creating a dictionary
founder = {'Apple': 'Steve Jobs', 'Microsoft': 'Bill Gates'}

# formatting
print('{f[Microsoft]} {f[Apple]}'.format(f = founder))
```

**输出:**

```python
Bill Gates Steve Jobs
```

`f[Microsoft]` 被比尔·盖茨取代，`f[Apple]` 被史蒂夫·乔布斯取代。

### 对于名单

```python
# creating a list
list_items = [1, 3, 5, 7, 9, 11]

# formatting
print('{l[3]} {l[5]}'.format(l = list_items))
```

**输出:**

```python
7 11
```

## 访问支持 `getattr()` 的对象的属性

### 为了上课

```python
# creating a class
class Program(object):
    language = 'Python'

# formatting
print('{p.language}'.format(p = Program()))
```

**输出:**

```python
Python
```

由于 `language` 是 `Program` 的属性，所以用 `Python` 代替了 `p.language`。

### 访问嵌套结构

```python
# creating a class
class Program(object):
    language = 'Python'

    # creating a dictionary
    versions = [{'version': '1'}, {'version': '2'}, {'version': '3'}]

# formatting
print('{p.language}: {p.versions[2][version]}'.format(p = Program()))
```

**输出:**

```python
Python: 3
```