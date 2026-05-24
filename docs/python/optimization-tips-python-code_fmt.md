# Python 代码的优化技巧

> 原文：[https://www.geeksforgeeks.org/optimization-tips-python-code/](https://www.geeksforgeeks.org/optimization-tips-python-code/)

在本文中，讨论了一些有趣的 Python 代码优化技巧。这些技术有助于在 python 代码中更快地产生结果。

## 1. 使用内置函数和库

内置函数如 `map()` 是用 C 代码实现的。因此解释器不必执行循环，这带来了相当可观的速度提升。
`map()` 函数将一个函数应用于可迭代对象的每个成员并返回结果。如果有多个参数，`map()` 返回一个由包含所有可迭代对象中对应项的元组组成的列表。

```py
# Python program to illustrate library functions
# save time while coding with the example of map()
import time

# slower (Without map())
start = time.clock()
s = 'geeks'
U = []
for c in s:
    U.append(c.upper())
print (U)
elapsed = time.clock()
e1 = elapsed - start
print ("Time spent in function is: ", e1)

# Faster (Uses builtin function map())
s = 'geeks'
start = time.clock()
U = map(str.upper, s)
print (U)
elapsed = time.clock()
e2 = elapsed - start
print ("Time spent in builtin function is: ", e2)
```

**输出：**

```py
['G', 'E', 'E', 'K', 'S']
Time spent in function is:  0.0394747945637
['G', 'E', 'E', 'K', 'S']
Time spent in builtin function is:  0.0212335531192
```

这些包是特定于平台的，这意味着我们需要适合我们正在使用的平台的包。如果我们正在进行字符串操作，可以考虑使用一个现有的模块“集合”，如 `deque`，该模块针对我们的目的进行了高度优化。

```py
# Python program to illustrate
# importing list-like container with
# fast appends and pops on either end
from collections import deque
s = 'geek'

# make a new deque
d = deque(s)

# add a new entry to the right side
d.append('y')

# add a new entry to the left side
d.appendleft('h')
print (d)

d.pop() # return and remove the rightmost item

d.popleft() # return and remove the lefttmost item

# print list deque in reverse
print (list(reversed(d)))
```

**输出：**

```py
deque(['h', 'g', 'e', 'e', 'k', 'y'])
['k', 'e', 'e', 'g']
```

```py
# importing iteration tools
import itertools
iter = itertools.permutations([1,2,3])
print (list(iter))
```

**输出：**

```py
[(1, 2, 3), (1, 3, 2), (2, 1, 3), (2, 3, 1), (3, 1, 2), (3, 2, 1)]
```

## 2. 使用键进行排序

在 Python 中，我们应该使用内置排序的 `key` 参数，这是一种更快的排序方式。

```py
# Python program to illustrate
# using keys for sorting
somelist = [1, -3, 6, 11, 5]
somelist.sort()
print (somelist)

s = 'geeks'
# use sorted() if you don't want to sort in-place:
s = sorted(s)
print (s)
```

**输出：**

```py
[-3, 1, 5, 6, 11]
['e', 'e', 'g', 'k', 's']
```

在每种情况下，列表都根据您选择作为键参数一部分的索引进行排序。这种方法对字符串和对数字一样有效。

## 3. 优化循环

编写地道的代码：这可能听起来有违直觉，但在大多数情况下，编写地道的代码会使您的代码更快。这是因为 Python 被设计为只有一种明显/正确的方法来完成一项任务。
例如（字符串连接）：

```py
# Python program to illustrate using
# optimized loops for faster coding

# slow O(n^2) - ( Note: In latest implementations it is O(n) )
s = 'hellogeeks'
slist = ''
for i in s:
    slist = slist + i
print (slist)

# string concatenation (idiomatic and fast O(n))
st = 'hellogeeks'
slist = ''.join([i for i in s])
print (slist)

# Better way to iterate a range
evens = [ i for i in range(10) if i%2 == 0]
print (evens)

# Less faster
i = 0
evens = []
while i < 10:
    if i %2 == 0:
        evens.append(i)
        i += 1
        print (evens)

# slow
v = 'for'
s = 'geeks ' + v + ' geeks'
print (s)

# fast
s = 'geeks %s geeks' % v
print (s)
```

**输出：**

```py
hellogeeks
[0, 2, 4, 6, 8]
geeks for geeks
```

每次运行到 `s(i)` 的循环时，Python 都会评估该方法。但是，如果您将评估放在一个变量中，该值已经是已知的，Python 可以更快地执行任务。

## 4. 尝试多种编码方法

每次创建应用程序时都使用完全相同的编码方法，几乎肯定会导致某些情况下应用程序运行速度比可能的速度慢。
例如（初始化字典元素）：

```py
# Python program to illustrate trying
# multiple coding approaches
# for getting faster result
# slower
mydict = {'g':1,'e':1,'e':1,'k':1}
word = 'geeksforgeeks'
for w in word:
    if w not in mydict:
        mydict[w] = 0
    mydict[w] += 1
print (mydict)

# faster
mydict = {'g':1,'e':1,'e':1,'k':1}
word = 'geeksforgeeks'
for w in word:
    try:
        mydict[w] += 1
    except KeyError:
        mydict[w] = 1
print (mydict)
```

**输出：**

```py
{'e': 5, 'g': 3, 'f': 1, 'k': 3, 'o': 1, 's': 2, 'r': 1}
```

两种情况下的输出都是相同的。唯一的区别是输出是如何获得的。

## 5. 使用 `xrange` 代替 `range`

`range()` – 这返回使用 `range()` 函数创建的数字列表。
`xrange()` – 此函数返回生成器对象，该对象只能通过循环来显示数字。只按需显示特定范围，因此称为“惰性求值”。

```py
# slower
x = [i for i in range(0,10,2)]
print (x)

# faster
x = [i for i in range(0,10,2)]
print (x)
```

**输出：**

```py
[1, 3, 5, 7, 9]
```

这可以节省系统内存，因为 `xrange()` 一次只能在一个序列中产生一个整数元素。而 `range()`，它给你一个完整的列表，这对于循环来说是不必要的开销。

## 6. 使用 Python 多重赋值交换变量

这在 Python 中是优雅且更快的。

```py
# Python program to illustrate swapping
# of a variable in one line

# slower
x = 2
y = 5
temp = x
x = y
y = temp
print (x,y)

x,y = 3,5
# faster
x, y = y, x
print (x,y)
```

**输出：**

```py
5 2
5 3
```

## 7. 如果可能，使用局部变量

Python 检索局部变量比检索全局变量更快。也就是说，避免使用 `global` 关键字。因此，如果您要经常访问一个方法（在循环内部），考虑将其写入一个变量。

```py
# Python program to illustrate trying
# to use local variables to make code
# run faster
class Test:
    def func(self,x):
        print (x+x)

# Declaring variable that assigns class method object
Obj = Test()
mytest = Obj.func # Declaring local variable
n = 2
for i in range(n):
    mytest(i) # faster than Obj.func(i)
```

**输出：**

```py

```

**参考文献：**

*   叠置溢出
*   [Python.org](https://wiki.python.org/moin/PythonSpeed/PerformanceTips)

本文由 **阿夫扎尔·安萨里** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。