# Python–避免定界符最后出现

> 原文: [https://www.geeksforgeeks.org/python-avoid-last-occurrence-of-delimitter/](https://www.geeksforgeeks.org/python-avoid-last-occurrence-of-delimitter/)

给定一个整数列表，使用分隔符执行连接，避免在末尾使用额外的分隔符。

> **输入**: `test_list = [4, 7, 8, 3, 2, 1, 9]`，`delim = "*"`
> **输出**: `4*7*8*3*2*1*9`
> **解释**: 避免了串联中经常出现的后置“*”。
>
> **输入**: `test_list = [4, 7, 8, 3]`，`delim = "*"`
> **输出**: `4*7*8*3`
> **解释**: 避免了通常出现在串联中的后面“*”。

## 方法一: 使用字符串切片

在这种情况下，我们使用字符串切片从形成后的字符串中切下最后一个字符。

### Python 3

```py
# Python3 code to demonstrate working of
# Avoid Last occurrence of delimitter
# Using map() + join() + str()

# initializing list
test_list = [4, 7, 8, 3, 2, 1, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing delim
delim = "$"

# appending delim to join
# will leave stray "$" at end
res = ''
for ele in test_list:
    res += str(ele) + "$"

# removing last using slicing
res = res[:len(res) - 1]

# printing result
print("The joined string : " + str(res))
```

**输出**

```py
The original list is : [4, 7, 8, 3, 2, 1, 9]
The joined string : 4$7$8$3$2$1$9
```

## 方法二: 使用 `map()` + `join()` + `str()`

在这种情况下，我们完全避免使用循环方法来解决这个问题，而是使用 `map()` 来转换为字符串，并使用 `join()` 来执行 join 任务。

### Python 3

```py
# Python3 code to demonstrate working of
# Avoid Last occurrence of delimitter
# Using map() + join() + str()

# initializing list
test_list = [4, 7, 8, 3, 2, 1, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing delim
delim = "$"

# map extends string conversion logic
res = delim.join(map(str, test_list))

# printing result
print("The joined string : " + str(res))
```

**输出**

```py
The original list is : [4, 7, 8, 3, 2, 1, 9]
The joined string : 4$7$8$3$2$1$9
```