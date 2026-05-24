# Python 中的数组 | 集合 1（介绍和函数）

> 原文：[https://www.geeksforgeeks.org/array-python-set-1-introduction-functions/](https://www.geeksforgeeks.org/array-python-set-1-introduction-functions/)

除了像[列表](https://www.geeksforgeeks.org/python-set-3-strings-lists-tuples-iterations/)这样的通用容器之外，Python 在其定义中也可以处理具有指定数据类型的容器。这个数组可以通过一个名为`array`的模块在 python 中处理。当我们只需要操作特定的数据类型值时，它们会很有用。

## 阵列上的操作

1.  `array(data_type, value_list)`：该函数用于**创建**一个数组，数组的参数中指定了数据类型和值列表。下表中提到了一些数据类型。

| 类型代码 | C 类型 | Python 类型 | 最小字节数 |
| :--- | :--- | :--- | :--- |
| `'b'` | signed char | int | 1 |
| `'B'` | unsigned char | int | 1 |
| `'u'` | Py_UNICODE | unicode character | 2 |
| `'h'` | signed short | int | 2 |
| `'H'` | unsigned short | int | 2 |
| `'i'` | signed int | int | 2 |
| `'I'` | unsigned int | int | 2 |
| `'l'` | signed long | int | 4 |
| `'L'` | unsigned long | int | 4 |
| `'q'` | signed long long | int | 8 |
| `'Q'` | unsigned long long | int | 8 |
| `'f'` | float | float | 4 |
| `'d'` | double | float | 8 |

2.  `append()`：该函数用于**在数组的**末尾**添加其参数中提到的值**。
3.  `insert(i, x)`：该函数用于将参数中指定的第 `i` 个位置处的值(`x`)相加。

## Python 代码示例

```py
# Python code to demonstrate the working of
# array(), append(), insert()

# importing "array" for array operations
import array

# initializing array with array values
# initializes array with signed integers
arr = array.array('i', [1, 2, 3])

# printing original array
print ("The new created array is : ",end=" ")
for i in range (0, 3):
    print (arr[i], end=" ")

print("\r")

# using append() to insert new value at end
arr.append(4);

# printing appended array
print("The appended array is : ", end="")
for i in range (0, 4):
    print (arr[i], end=" ")

# using insert() to insert value at specific position
# inserts 5 at 2nd position
arr.insert(2, 5)

print("\r")

# printing array after insertion
print ("The array after insertion is : ", end="")
for i in range (0, 5):
    print (arr[i], end=" ")
```

**输出：**

```py
The new created array is : 1 2 3 
The appended array is : 1 2 3 4 
The array after insertion is : 1 2 5 3 4 
```

4.  `pop()`：此函数**移除其参数中提到的位置**处的元素并将其返回。
5.  `remove()`：该函数用于**删除其参数中提到的值的第一个出现的**。

## Python 代码示例

```py
# Python code to demonstrate the working of
# pop() and remove()

# importing "array" for array operations
import array

# initializing array with array values
# initializes array with signed integers
arr= array.array('i',[1, 2, 3, 1, 5])

# printing original array
print ("The new created array is : ",end="")
for i in range (0,5):
    print (arr[i],end=" ")

print ("\r")

# using pop() to remove element at 2nd position
print ("The popped element is : ",end="")
print (arr.pop(2));

# printing array after popping
print ("The array after popping is : ",end="")
for i in range (0,4):
    print (arr[i],end=" ")

print("\r")

# using remove() to remove 1st occurrence of 1
arr.remove(1)

# printing array after removing
print ("The array after removing is : ",end="")
for i in range (0,3):
    print (arr[i],end=" ")
```

**输出：**

```py
The new created array is : 1 2 3 1 5 
The popped element is : 3
The array after popping is : 1 2 1 5 
The array after removing is : 2 1 5 
```

6.  `index()`：该函数返回参数中提到的值的第一次出现的**索引**。
7.  `reverse()`：此功能**反转**数组。

## Python 代码示例

```py
# Python code to demonstrate the working of
# index() and reverse()

# importing "array" for array operations
import array

# initializing array with array values
# initializes array with signed integers
arr= array.array('i',[1, 2, 3, 1, 2, 5])

# printing original array
print ("The new created array is : ",end="")
for i in range (0,6):
    print (arr[i],end=" ")

print ("\r")

# using index() to print index of 1st occurrence of 2
print ("The index of 1st occurrence of 2 is : ",end="")
print (arr.index(2))

#using reverse() to reverse the array
arr.reverse()

# printing array after reversing
print ("The array after reversing is : ",end="")
for i in range (0,6):
    print (arr[i],end=" ")
```

**输出：**

```py
The new created array is : 1 2 3 1 2 5 
The index of 1st occurrence of 2 is : 1
The array after reversing is : 5 2 1 3 2 1
```

**参考：**
[https://docs.python.org/3/library/array.html#module-array](https://docs.python.org/3/library/array.html#module-array)

本文由 [**Manjeet Singh**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。