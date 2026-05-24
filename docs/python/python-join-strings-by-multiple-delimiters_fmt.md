# Python–通过多个分隔符连接字符串

> 原文: [https://www.geeksforgeeks.org/python-join-strings-by-multiple-delimiters/](https://www.geeksforgeeks.org/python-join-strings-by-multiple-delimiters/)

给定两个字符串，任务是编写一个 Python 程序，通过分隔符列表中的每个分隔符将它们连接起来。

> **输入:** `test_str1 = 'Geeksforgeeks'`，`test_str2 = 'Best'`，`join_list = ["+", "*", "-", "$", ",", "@"]`
>
> **输出:** `['Geeksforgeeks+Best', 'Geeksforgeeks*Best', 'Geeksforgeeks-Best', 'Geeksforgeeks$Best', 'Geeksforgeeks,Best', 'Geeksforgeeks@Best']`
>
> **解释:** 元素与所有需要的分隔符连接在一起。
>
> **输入:** `test_str1 = 'Geeksforgeeks'`，`test_str2 = 'Best'`，`join_list = ["+", "*", "-", "$"]`
>
> **输出:** `['Geeksforgeeks+Best', 'Geeksforgeeks*Best', 'Geeksforgeeks-Best', 'Geeksforgeeks$Best']`
>
> **解释:** 元素与所有需要的分隔符连接在一起。

## 方法一: 使用列表推导

在这种情况下，我们使用循环内部列表推导和 `+` 运算符执行连接任务来迭代列表中的所有分隔符。

### 示例

```py
# initializing strings
test_str1 = 'Geeksforgeeks'
test_str2 = "Best"

# printing original strings
print("The original string 1 is : " + str(test_str1))
print("The original string 2 is : " + str(test_str2))

# initializing join list
join_list = ["+", "*", "-", "$", ",", "@"]

# + operator used for concatenations
res = [test_str1 + delim + test_str2 for delim in join_list]

# printing result
print("All delimiters concatenations : " + str(res))
```

### 输出

> The original string 1 is : Geeksforgeeks
>
> The original string 2 is : Best
>
> All delimiters concatenations : ['Geeksforgeeks+Best', 'Geeksforgeeks*Best', 'Geeksforgeeks-Best', 'Geeksforgeeks$Best', 'Geeksforgeeks,Best', 'Geeksforgeeks@Best']

## 方法二: 使用 `join()` 和列表推导

与上述方法类似，区别在于连接任务是使用 `join()` 而不是 `+` 运算符执行的。

### 示例

```py
# initializing strings
test_str1 = 'Geeksforgeeks'
test_str2 = "Best"

# printing original strings
print("The original string 1 is : " + str(test_str1))
print("The original string 2 is : " + str(test_str2))

# initializing join list
join_list = ["+", "*", "-", "$", ",", "@"]

# join() operator used for concatenations
res = [delim.join([test_str1, test_str2]) for delim in join_list]

# printing result
print("All delimiters concatenations : " + str(res))
```

### 输出

> The original string 1 is : Geeksforgeeks
>
> The original string 2 is : Best
>
> All delimiters concatenations : ['Geeksforgeeks+Best', 'Geeksforgeeks*Best', 'Geeksforgeeks-Best', 'Geeksforgeeks$Best', 'Geeksforgeeks,Best', 'Geeksforgeeks@Best']