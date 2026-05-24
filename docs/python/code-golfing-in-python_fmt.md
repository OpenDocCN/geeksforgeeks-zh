# Python 中的代码高尔夫

> 原文:[https://www.geeksforgeeks.org/code-golfing-in-python/](https://www.geeksforgeeks.org/code-golfing-in-python/)

**Python 中的 Code Golf** 指的是尝试使用尽可能少的字符来解决问题。就像在高尔夫球中，得分低的人获胜，最少数量的角色“获胜”。

[Python](https://www.geeksforgeeks.org/python-programming-language/) 由于向后兼容性、怪癖、它是一种高级语言以及所有的强制，是一种非常棒的代码高尔夫语言。因此，这里我们将看看 Python 语言中的一些代码高尔夫技巧。

## 使用循环

### 折叠两个数字循环

假设你正在迭代一个由 `m` 行和 `n` 列组成的矩阵。使用单个循环迭代 `m*n` 矩阵通常会更短，而不是两个嵌套的循环，一个用于行，一个用于列。

**原码:**

```py
m = n = 3
for i in range(m):
    for j in range(n):
        print(i, j)
```

**高尔夫代码:**

```py
m = n = 3
for i in range(m*n):
    print(i//n, i%n)
```

这项技术不仅限于两个嵌套循环，我们甚至可以为 3 个或更多嵌套循环编写相同的循环

```py
m, n, o = 2, 3, 4
for k in range(m*n*o):
    print(k//n//o, k%(n*o), k%o)
```

## 使用运算符

### 加 1 或减 1

对于整数 `n`，可以写 `-~n` 相当于 `n+1`，`~-n` 相当于 `n-1`。

这个工作原理是因为位翻转 `~x` 等于 `-x-1`。这使用相同数量的字符，但可以间接切割空格或括号以获得运算符优先级。

### Membership in Set

我们在 Python 中写集合为 `S = {1, 2, 3, 4, 5}`。要检查元素 `e` 是否存在于集合 `S` 中，我们可以检查条件 `{e}&S`。

**原码:**

```py
S = {1, 2, 3, 4, 5, 6, 7}
if 5 in S:
    print("Present")
else:
    print("Absent")
```

**高尔夫代码:**

```py
S = {1, 2, 3, 4, 5, 6, 7}
if {5}&S:
    print("Present")
else:
    print("Absent")
```

### Sibling of AND operator

当我们有两个布尔或整数值 `a` 和 `b`，如果我们想找出 `a` 和 `b` 是否都为真，使用 `*` 代替 `and`。

**原码:**

```py
if a and b:
    print("geeks")
else:
    print("geeksforgeeks")
```

**高尔夫代码:**

```py
if a*b:
    print("geeks")
else:
    print("geeksforgeeks")
```

### Sibling of OR operator

当我们有两个布尔或整数值 `a` 和 `b`，如果我们想找出 `a` 和 `b` 中是否有一个为真或两者都为真，使用 `|` 代替 `or`。

**原码:**

```py
if a or b:
    print("geeks")
else:
    print("geeksforgeeks")
```

**高尔夫代码:**

```py
if a|b:
    print("geeks")
else:
    print("geeksforgeeks")
```

### Use += instead of append

代替使用 `append` 向现有列表添加一个项目，我们可以使用 `+=` 运算符。

**原码:**

```py
A.append(B)
```

**高尔夫代码:**

```py
A+=B,
```

**注意:** `B,` 这里创建一个一元元组，可以像 `A+=[B]` 中的 `[B]` 一样用来扩展 `A`。

### Use += instead of extend

代替使用 `extend` 将一个列表合并到另一个列表的末尾，我们可以使用 `+=` 运算符。

**原码:**

```py
A.extend(B)
```

**高尔夫代码:**

```py
A+=B
```

### 神奇的比较运算符

我们面临很多情况，需要比较一个单个变量的不同值，一般我们通过不同的比较并结合 `and` 运算符来进行辩护。但是 Python 允许我们将所有的比较运算符放在一行中，而不使用 `and` 运算符。

**原码:**

```py
if a>1 and a<10:
    print(a)
```

**高尔夫代码:**

```py
if 1<a<10:
    print(a)
```

**注意:** 我们也可以同时对多个变量使用这个技巧。

**原码:**

```py
if a > 10 and b > 10 and 30 > a and 50 > b:
    print(a)
```

**高尔夫代码:**

```py
if 30 > a > 10 < b < 50:
    print(a)
```

## 使用函数

### Sibling of Floor function

假设我们想要找到一个实数的向下取整值，我们通常从 `math` 导入 `floor` 函数，然后应用到数字上。但我们可以简单地应用 floor 除法与 1，这将给我们一个有益的结果。

**原码:**

```py
from math import floor
n = 3/2
print(floor(n))
```

**高尔夫代码:**

```py
n = 3/2
print(n//1)
```

### Sibling of Ceil function

假设我们想要找到一个实数的向上取整值，我们通常从 `math` 导入 `ceil` 函数，然后应用到数字上。但我们可以通过首先乘以 -1，然后应用 floor 除法与 1，再乘以 -1 来以更漂亮的方式完成此操作。

**原码:**

```py
from math import ceil
n = 3/2
print(ceil(n))
```

**高尔夫代码:**

```py
n = 3/2
print(-(-n//1))
```

### Lambda functions

Lambda 定义不包括 `return` 语句，它总是包含一个被返回的表达式。我们也可以将 lambda 定义放在任何需要函数的地方，我们根本不必将其分配给变量。这就是 lambda 函数的简单性。

**原码:**

```py
def c(a):
  if a < 3: return a-5
  else: return a+5
```

**高尔夫代码:**

```py
c=lambda a:a<3and a-5or a+5
```

### To get the entire alphabet string

我们可以使用 Python 的 `map` 函数来获取整个字母表集合的字符串。

**原码:**

```py
string = 'abcdefghijklmnopqrstuvwxyz'
or 
string = [chr(i+97)for i in range(26)]
```

**高尔夫代码:**

```py
string = map(chr,range(97,123))
```

## 使用索引

### Indexing Technique for conditions

当我们有一个特定的条件，其答案以小整数的形式给出时，我们可以在列表或元组的整数索引中使用它来获得最终答案。

**原码:**

```py
if a<b:return a
else:return b
```

**高尔夫代码:**

```py
return (b, a)[a<b]
```

### Reverse the Sequence

我们可以使用好的外星人笑脸来反转任何列表序列。

**原码:**

```py
string = 'geeksforgeeks'
for i in range(len(string)-1,-1,-1):
    print(string[i])
```

**高尔夫代码:**

```py
string = 'geeksforgeeks'
for i in string[::-1]:
    print(i)
```

### Use ~ to index from the back of a list

如果 `L` 是一个列表，使用 `L[~i]` 来获取从后往前数的第 `i` 个元素。这是 `L` 的反转列表的第 `i` 个元素。位补码 `~i` 等于 `-i-1`，因此修正了 `L[-i]` 的差一错误。

**原码:**

```py
string = 'geeksforgeeks'
for i in range(len(string)-1,-1,-1):
    print(string[i])
```

**高尔夫代码:**

```py
for i in range(len(string)):
    print(string[~i])
```

### Print the items of the list

我们可以通过使用 `*` 运算符与列表的名称来打印列表的项目，而不是循环遍历列表。

**原码:**

```py
A = [1,2,3,4,5,6,7]
for i in A:
    print(i,end = ' ')
```

**高尔夫代码:**

```py
A = [1,2,3,4,5,6,7]
print(*A) 
```

## 使用分配

### 给多个变量赋值相同

我们可以在一行或多行中给多个变量赋值相同的值。

**原码:**

```py
# multiple lines
a = 0
b = 0
c = 0

# single line
a,b,c = 0,0,0
```

**高尔夫代码:**

```py
a = b = c = 0
```

### 给变量分配相同或不同的字符

我们可以在一行或多行中给多个变量分配相同或不同的字符。

**原码:**

```py
# multiple lines
a = 'p'
b = 'q'
c = 'r'

# single line
a,b,c = 'p','q','r'
```

**高尔夫代码:**

```py
a,b,c = 'pqr'
```

## 使用转换

### Converting iterables into the list

想象你有一个有序的可迭代对象，如元组或字符串，但你想将其转换为列表，那么你可以使用 `*` 运算符来实现。

**原码:**

```py
a = (2,3,5,7,11)
x = list(a)

a = 'geeksforgeek'
x = list(a)
```

**高尔夫代码:**

```py
a = (2,3,5,7,11)
*x, = a

a = 'geeksforgeeks'
*x, = a
```

### Converting iterables into the Set

想象你有一个可迭代对象，如列表、元组或字符串，但你想将其转换为集合，那么你可以使用 `*` 运算符来实现。

**原码:**

```py
a = (2,3,5,7,11)
x = set(a)

a = [2,3,5,7,11]
x = set(a)

a = 'geeksforgeeks'
x = set(a)
```

**高尔夫代码:**

```py
a = (2,3,5,7,11)
x = {*a}

a = [2,3,5,7,11]
x = {*a}

a = 'geeksforgeeks'
x = {*a}
```

### Converting iterables into the Tuple

想象你有一个可迭代对象，如列表、集合或字符串，但你想将其转换为元组，那么你可以使用 `*` 运算符来实现。

**原码:**

```py
a = (2,3,5,7,11)
x = tuple(a)

a = [2,3,5,7,11]
x = tuple(a)

a = 'geeksforgeeks'
x = tuple(a)
```

**高尔夫代码:**

```py
a = (2,3,5,7,11)
x = (*a,)

a = [2,3,5,7,11]
x = (*a,)

a = 'geeksforgeeks'
x = (*a,)
```

## 在不同材料的连接过程中

### Joining multiple Lists

我们可以使用 `+` 运算符来连接多个列表，但对于代码高尔夫，我们可以使用 `*` 运算符来做同样的事情。

**原码:**

```py
T = [2,3,4,5,6,7,8,9]
new_T = [1]+T+[10]
```

**高尔夫代码:**

```py
T = [2,3,4,5,6,7,8,9]
new_T = [1,*T,10]
```

### Joining multiple Tuples

我们可以使用 `+` 运算符来连接多个元组，但对于代码高尔夫，我们可以使用 `*` 运算符来做同样的事情。

**原码:**

```py
T = (2,3,4,5,6,7,8,9)
new_T = (1,)+T+(10,)
```

**高尔夫代码:**

```py
T = (2,3,4,5,6,7,8,9)
new_T = (1,*T,10)
```