# Python 中的运算符函数 | 集合 2

> 原文: [https://www.geeksforgeeks.org/operator-functions-python-set-2/](https://www.geeksforgeeks.org/operator-functions-python-set-2/)
> 参见: [Python 中的运算符函数 | 集合 1](https://www.geeksforgeeks.org/operator-functions-in-python-set-1/)

本文将讨论更多的函数。

## 1. `setitem(ob, pos, val)`

此函数用于在容器的特定位置分配值。
操作：`ob[pos] = val`

## 2. `delitem(ob, pos)`

此函数用于删除容器中特定位置的值。
操作：`del ob[pos]`

## 3. `getitem(ob, pos)`

此函数用于获取容器中特定位置的值。
操作：`ob[pos]`

### 示例代码

```python
# Python code to demonstrate working of 
# setitem(), delitem() and getitem()

# importing operator module 
import operator

# Initializing list
li = [1, 5, 6, 7, 8]

# printing original list 
print ("The original list is : ",end="")
for i in range(0,len(li)):
    print (li[i],end=" ")

print ("\r")

# using setitem() to assign 3 at 4th position
operator.setitem(li,3,3)

# printing modified list after setitem()
print ("The modified list after setitem() is : ",end="")
for i in range(0,len(li)):
    print (li[i],end=" ")

print ("\r")

# using delitem() to delete value at 2nd index
operator.delitem(li,1)

# printing modified list after delitem()
print ("The modified list after delitem() is : ",end="")
for i in range(0,len(li)):
    print (li[i],end=" ")

print ("\r")

# using getitem() to access 4th element
print ("The 4th element of list is : ",end="")
print (operator.getitem(li,3))
```

### 输出

```python
The original list is : 1 5 6 7 8 
The modified list after setitem() is : 1 5 6 3 8 
The modified list after delitem() is : 1 6 3 8 
The 4th element of list is : 8
```

## 4. `setitem(ob, slice(a, b), val)`

此函数用于设置容器中特定范围内的值。
操作：`obj[a:b] = val`

## 5. `delitem(ob, slice(a, b))`

操作：`del obj[a:b]`

## 6. `getitem(ob, slice(a, b))`

操作：`obj[a:b]`

### 示例代码

```python
# Python code to demonstrate working of 
# setitem(), delitem() and getitem()

# importing operator module 
import operator

# Initializing list
li = [1, 5, 6, 7, 8]

# printing original list 
print ("The original list is : ",end="")
for i in range(0,len(li)):
    print (li[i],end=" ")

print ("\r")

# using setitem() to assign 2,3,4 at 2nd,3rd and 4th index
operator.setitem(li,slice(1,4),[2,3,4])

# printing modified list after setitem()
print ("The modified list after setitem() is : ",end="")
for i in range(0,len(li)):
    print (li[i],end=" ")

print ("\r")

# using delitem() to delete value at 3rd and 4th index
operator.delitem(li,slice(2,4))

# printing modified list after delitem()
print ("The modified list after delitem() is : ",end="")
for i in range(0,len(li)):
    print (li[i],end=" ")

print ("\r")

# using getitem() to access 1st and 2nd element
print ("The 1st and 2nd element of list is : ",end="")
print (operator.getitem(li,slice(0,2)))
```

### 输出

```python
The original list is : 1 5 6 7 8 
The modified list after setitem() is : 1 2 3 4 8 
The modified list after delitem() is : 1 2 8 
The 1st and 2nd element of list is : [1, 2]
```

## 7. `concat(obj1, obj2)`

此函数用于连接两个容器。
操作：`obj1 + obj2`

## 8. `contains(obj1, obj2)`

此函数用于检查 `obj2` 是否存在于 `obj1` 中。
操作：`obj2 in obj1`

### 示例代码

```python
# Python code to demonstrate working of 
# concat() and contains()

# importing operator module 
import operator

# Initializing string 1
s1 = "geeksfor"

# Initializing string 2
s2 = "geeks"

# using concat() to concatenate two strings
print ("The concatenated string is : ",end="")
print (operator.concat(s1,s2))

# using contains() to check if s1 contains s2
if (operator.contains(s1,s2)):
       print ("geeksfor contains geeks")
else : print ("geeksfor does not contain geeks")
```

### 输出

```python
The concatenated string is : geeksforgeeks
geeksfor contains geeks
```

## 9. `and_(a, b)`

此函数用于计算参数的位与（bitwise AND）。
操作：`a & b`

## 10. `or_(a, b)`

此函数用于计算参数的位或（bitwise OR）。
操作：`a | b`

## 11. `xor(a, b)`

此函数用于计算参数的位异或（bitwise XOR）。
操作：`a ^ b`

## 12. `invert(a)`

此函数用于计算参数的位取反（bitwise inversion）。
操作：`~ a`

### 示例代码

```python
# Python code to demonstrate working of 
# and_(), or_(), xor(), invert()

# importing operator module 
import operator

# Initializing a and b
a = 1
b = 0

# using and_() to display bitwise and operation
print ("The bitwise and of a and b is : ",end="")
print (operator.and_(a,b))

# using or_() to display bitwise or operation
print ("The bitwise or of a and b is : ",end="")
print (operator.or_(a,b))

# using xor() to display bitwise exclusive or operation
print ("The bitwise xor of a and b is : ",end="")
print (operator.xor(a,b))

# using invert() to invert value of a
operator.invert(a)

# printing modified value
print ("The inverted value of a is : ",end="")
print (operator.invert(a))
```

### 输出

```python
The bitwise and of a and b is : 0
The bitwise or of a and b is : 1
The bitwise xor of a and b is : 1
The inverted value of a is : -2
```

本文由 [**Manjeet Singh**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在 GeeksforGeeks 主页上，帮助其他 Geeks。

如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。