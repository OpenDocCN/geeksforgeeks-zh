# 在 Python 中平分算法函数

> 原文: [https://www.geeksforgeeks.org/bisect-algorithm-functions-in-python/](https://www.geeksforgeeks.org/bisect-algorithm-functions-in-python/)

平分算法的目的是在列表中找到一个需要插入元素的位置，以保持列表的排序。

Python 在其定义中使用模块 `bisect` 提供了二等分算法，该模块允许在插入每个元素后保持列表的排序顺序。这一点非常重要，因为这样可以减少在插入每个元素后对列表进行一次又一次排序所需的开销时间。

## 查找插入位置的函数

### 1. `bisect(list, num, beg, end)`
该函数返回排序的列表中的位置，在该位置可以放置参数中传递的数字，以便按照排序顺序维护结果列表。如果该元素已经存在于列表中，则返回必须插入该元素的最右侧位置。这个函数有 4 个参数：需要处理的列表，需要插入的数字，需要考虑的列表起始位置，需要考虑的结束位置。

### 2. `bisect_left(list, num, beg, end)`
该函数返回排序的列表中的位置，在该位置可以放置参数中传递的数字，以便按照排序顺序维护结果列表。如果该元素已经存在于列表中，则返回必须插入该元素的最左侧位置。这个函数有 4 个参数：需要处理的列表，需要插入的数字，需要考虑的列表起始位置，需要考虑的结束位置。

### 3. `bisect_right(list, num, beg, end)`
这个函数的工作原理类似于上面提到的 `bisect()`。

```py
# Python code to demonstrate the working of
# bisect(), bisect_left() and bisect_right()

# importing "bisect" for bisection operations
import bisect

# initializing list
li = [1, 3, 4, 4, 4, 6, 7]

# using bisect() to find index to insert new element
# returns 5 ( right most possible index )
print ("The rightmost index to insert, so list remains sorted is  : ", end="")
print (bisect.bisect(li, 4))

# using bisect_left() to find index to insert new element
# returns 2 ( left most possible index )
print ("The leftmost index to insert, so list remains sorted is  : ", end="")
print (bisect.bisect_left(li, 4))

# using bisect_right() to find index to insert new element
# returns 4 ( right most possible index )
print ("The rightmost index to insert, so list remains sorted is  : ", end="")
print (bisect.bisect_right(li, 4, 0, 4))
```

输出:

```py
The rightmost index to insert, so list remains sorted is  : 5
The leftmost index to insert, so list remains sorted is  : 2
The rightmost index to insert, so list remains sorted is  : 4
```

时间复杂度:

```py
O(log(n)) -> Bisect method works on the concept of binary search
```

## 插入元素的函数

### 4. `insort(list, num, beg, end)`
该函数在适当的位置插入数字后返回排序列表，如果元素已经存在于列表中，则该元素被插入到最右边可能的位置。这个函数有 4 个参数：需要处理的列表，需要插入的数字，需要考虑的列表起始位置，需要考虑的结束位置。

### 5. `insort_left(list, num, beg, end)`
该函数在适当位置插入数字后返回排序列表，如果列表中已经存在该元素，则该元素被插入到最左侧可能的位置。这个函数有 4 个参数：需要处理的列表，需要插入的数字，需要考虑的列表起始位置，需要考虑的结束位置。

### 6. `insort_right(list, num, beg, end)`
这个函数的工作方式类似于上面提到的 `insort()`。

```py
# Python code to demonstrate the working of
# insort(), insort_left() and insort_right()

# importing "bisect" for bisection operations
import bisect

# initializing list
li1 = [1, 3, 4, 4, 4, 6, 7]

# initializing list
li2 = [1, 3, 4, 4, 4, 6, 7]

# initializing list
li3 = [1, 3, 4, 4, 4, 6, 7]

# using insort() to insert 5 at appropriate position
# inserts at 6th position
bisect.insort(li1, 5)

print ("The list after inserting new element using insort() is : ")
for i in range(0, 7):
    print(li1[i], end=" ")

# using insort_left() to insert 5 at appropriate position
# inserts at 6th position
bisect.insort_left(li2, 5)

print("\r")

print ("The list after inserting new element using insort_left() is : ")
for i in range(0, 7):
    print(li2[i], end=" ")

print("\r")

# using insort_right() to insert 5 at appropriate position
# inserts at 5th position
bisect.insort_right(li3, 5, 0, 4)

print ("The list after inserting new element using insort_right() is : ")
for i in range(0, 7):
    print(li3[i], end=" ")
```

输出:

```py
The list after inserting new element using insort() is : 
1 3 4 4 4 5 6 
The list after inserting new element using insort_left() is : 
1 3 4 4 4 5 6 
The list after inserting new element using insort_right() is : 
1 3 4 4 5 4 6
```

时间复杂度:

```py
O(n) -> Inserting an element in sorted array requires traversal
```

本文由 **曼吉特·辛格** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。