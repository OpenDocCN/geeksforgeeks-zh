# Python 中反转二进制位的不同方式

> 原文：[Different Ways to Invert the Binary Bits in Python](https://www.geeksforgeeks.org/different-ways-to-invert-the-binary-bits-in-python/)

我们知道数字的二进制值是什么样子。例如，`10`（数字十）的二进制值是`1010`（二进制值）。

有时需要反转位，即`0`到`1`（0 到 1）和`1`到`0`（1 到 0）。这里有几个方法可以让我们在 Python 中反转位。

## 方法一：使用循环
通过迭代每一位，我们可以将位`1`更改为位`0`，反之亦然。

```python
bit_s = '1010'
inverse_s = ''

for i in bit_s:
    if i == '0':
        inverse_s += '1'
    else:
        inverse_s += '0'

print("Inversed string is ", inverse_s)
```

**输出：**

```python
Inversed string is 0101
```

## 方法二：使用字典
字典访问一个元素非常快，需要 O(1) 的时间复杂度。

```python
# create a dictionary
b_dict = {'0': '1', '1': '0'}

bit_s = '1010'
inverse_s = ''

for i in bit_s:
    inverse_s += b_dict[i]

print("Inversed string is", inverse_s)
```

**输出：**

```python
Inversed string is 0101
```

## 方法三：使用列表理解
列表理解是访问、添加、操作列表的简写。

```python
bit_s = '1010'

# using ternary operator with list comprehension
inverse_s = ''.join(['1' if i == '0' else '0' for i in bit_s])

print("Inversed string is", inverse_s)
```

**输出：**

```python
Inversed string is 0101
```

## 方法四：使用字符串的 `replace()` 方法
在 Python 中，`strings` 有一个内置的方法，即 `string.replace(existing_characters, new_characters)`，用 `new_characters` 替换所有的 `existing_characters`。

```python
bit_s = '1010'

# replace "1" with "2"
# output : "2020"
inverse_s = bit_s.replace('1', '2')

# replace "0" with "1"
# output : "2121"
inverse_s = inverse_s.replace('0', '1')

# replace "0" with "1"
# output : "0101"
inverse_s = inverse_s.replace('2', '0')

print("Inversed string is", inverse_s)
```

**输出：**

```python
Inversed string is 0101
```

## 方法五：使用逐位异或运算符
如果一位为`1`，另一位为`0`，异或运算符返回`1`，否则返回假。

```python
bit_s = '1010'

# convert binary string into integer
temp = int(bit_s, 2)

# applying Ex-or operator b/w 10 and 31
inverse_s = temp ^ (2 ** (len(bit_s) + 1) - 1)

# convert the integer result into binary result and then slicing of the '0b1' binary indicator
rslt = bin(inverse_s)[3:]

# print the result
print("Inversed string is", rslt)
```

**输出：**

```python
Inversed string is 0101
```