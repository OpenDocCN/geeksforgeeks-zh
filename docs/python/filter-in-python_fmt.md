# Python 中的 `filter()`

> 原文: [https://www.geeksforgeeks.org/filter-in-python/](https://www.geeksforgeeks.org/filter-in-python/)

`filter()` 方法在测试序列中每个元素是否为真的函数的帮助下过滤给定的序列。

## 语法

```py
filter(function, sequence)
```

**参数:**
- `function`: 用于测试序列中每个元素是否为真的函数。
- `sequence`: 需要被过滤的序列，可以是集合、列表、元组或任何迭代器的容器。

**返回值:**
返回一个已经过滤好的迭代器。

## 示例

```py
# function that filters vowels
def fun(variable):
    letters = ['a', 'e', 'i', 'o', 'u']
    if (variable in letters):
        return True
    else:
        return False

# sequence
sequence = ['g', 'e', 'e', 'j', 'k', 's', 'p', 'r']

# using filter function
filtered = filter(fun, sequence)

print('The filtered letters are:')
for s in filtered:
    print(s)
```

**输出:**

```py
The filtered letters are:
e
e
```

## 应用

它通常与 [Lambda 函数](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)一起使用来分离列表、元组或集合。

```py
# a list contains both even and odd numbers. 
seq = [0, 1, 2, 3, 5, 8, 13]

# result contains odd numbers of the list
result = filter(lambda x: x % 2 != 0, seq)
print(list(result))

# result contains even numbers of the list
result = filter(lambda x: x % 2 == 0, seq)
print(list(result))
```

**输出:**

```py
[1, 3, 5, 13]
[0, 2, 8]
```

详见 [Python Lambda 函数](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)。