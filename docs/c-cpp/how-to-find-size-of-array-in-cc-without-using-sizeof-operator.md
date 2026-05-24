# 不使用 size of 如何在 C/C++ 中求数组的大小？

> 原文:[https://www . geesforgeks . org/如何在不使用 sizeof 运算符的情况下找到 cc 中的数组大小/](https://www.geeksforgeeks.org/how-to-find-size-of-array-in-cc-without-using-sizeof-operator/)

我们可以使用 size of 运算符找到数组的大小，如下所示。

```cpp
// Finds size of arr[] and stores in 'size'
int size = sizeof(arr)/sizeof(arr[0]);

```

**我们可以不使用 sizeof 运算符也这样做吗？**

**方法 1(编写我们自己的 sizeof)**
给定一个数组(你不知道数组中元素的类型)，不使用 sizeof 运算符求数组中元素的总数？

一种解决方案是编写我们自己的操作符大小(详见[这个](https://www.geeksforgeeks.org/implement-your-own-sizeof/)

```cpp
// C++ program to find size of an array by writing our
// sizeof
#include <bits/stdc++.h>
using namespace std;

// User defined sizeof macro
# define my_sizeof(type) ((char *)(&type+1)-(char*)(&type))

int main()
{
    int  arr[] = {1, 2, 3, 4, 5, 6};
    int size = my_sizeof(arr)/my_sizeof(arr[0]);

    cout << "Number of elements in arr[] is " 
         << size;

    return 0;
}
```

输出:

```cpp
Number of elements in arr[] is 6
```

**方法 2(使用指针破解)**
与上面的解决方案相比，下面的解决方案非常短。数组 A 中的元素数量可以通过表达式计算出来

```cpp
int size = *(&arr + 1) - arr;

```

```cpp
// C++ program to find size of an array by using a 
// pointer hack.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int  arr[] = {1, 2, 3, 4, 5, 6};
    int size = *(&arr + 1) - arr;
    cout << "Number of elements in arr[] is "
         << size;
    return 0;
}
```

输出:

```cpp
Number of elements in arr[] is 6
```

**这是如何工作的？**
这里指针算术发挥了它的作用。我们不需要显式地将每个位置转换成字符指针。

```cpp
&arr ==> Pointer to an array of 6 elements.
         [See this for difference between &arr
          and arr]   

(&arr + 1) ==> Address of 6 integers ahead as
               pointer type is pointer to array
               of 6 integers.

*(&arr + 1) ==> Same address as (&arr + 1), but 
                type of pointer is "int *".

*(&arr + 1) - arr ==> Since *(&arr + 1) points 
                   to the address 6 integers
                   ahead of arr, the difference
                   between two is 6\.          

```

本文由海得拉巴 JNTUH 工程学院 **Nikhil Chakravartula** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论