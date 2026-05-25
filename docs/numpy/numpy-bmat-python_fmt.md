## numpy.bmat()

> 哎哎哎: [https://www.geeksforgeeks.org/numpy-bmat-python/](https://www.geeksforgeeks.org/numpy-bmat-python/)

`numpy.bmat(obj, l_dict=None, g_dict=None)`：从嵌套对象返回专门化的二维矩阵，这些嵌套对象可以是类似字符串或类似数组的。

**参数:**

```py
object : array-like or string
l_dict : (dict, optional) replaces local operands,
         A dictionary that replaces local operands in current frame
g_dict : (dict, optional) replaces global operands,
         A dictionary that replaces global operands in current frame.
```

**返回:**

```py
2-D matrix from nested objects
```

```py
# Python Program illustrating
# numpy.bmat

import numpy as geek

A = geek.mat('4 1; 22 1')
B = geek.mat('5 2; 5 2')
C = geek.mat('8 4; 6 6')

# array like input
a = geek.bmat([[A, B], [C, A]])
print("Via bmat array like input : \n", a, "\n\n")

# string like input
s = geek.bmat('A, B; A, A')
print("Via bmat string like input : \n", s)
```

**输出:**

```py
Via bmat array like input :
 [[ 4  1  5  2]
 [22  1  5  2]
 [ 8  4  4  1]
 [ 6  6 22  1]]

Via bmat string like input :
 [[ 4  1  5  2]
 [22  1  5  2]
 [ 4  1  4  1]
 [22  1 22  1]]
```

**注意:**
这些代码不会在在线-ID上运行。请在您的系统上运行它们来探索工作的。
本文由 **Mohit Gupta_OMG 供稿😀**。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。