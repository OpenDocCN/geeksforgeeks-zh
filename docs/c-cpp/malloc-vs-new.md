# malloc()与新

的比较

> 原文:[https://www.geeksforgeeks.org/malloc-vs-new/](https://www.geeksforgeeks.org/malloc-vs-new/)

**下面是 malloc()和 operator new 之间的区别。** :

1.  **Call constructor:** The constructor is newly called, but malloc () does not. In fact, the original data types (char, int, float, etc.) can also be initialized with new ones. For example, the following program prints 10 sheets.

## CPP

```cpp
#include<iostream>
using namespace std;
int main()
{
    // Initialization with new()
    int *n = new int(10);
    cout << *n;
    getchar();
    return 0;
}
```

**输出:**

```cpp
10
```

**2。运算符 vs 函数:** new 是运算符，而 malloc()是函数。

**3。返回类型:** new 返回确切的数据类型，而 malloc()返回 void *。

**4。失败条件:**失败时，malloc()返回空值，其中作为新的抛出 bad_alloc 异常。

**5。内存:**如果是新的，内存从空闲存储区分配，在 malloc()中，内存分配是从堆中完成的。

**6。大小:**所需的内存大小是由编译器为 new 计算的，因为我们必须手动计算 malloc()的大小。

**7。缓冲区大小:** malloc()允许使用 realloc()更改缓冲区大小，而 new 则不允许

<figure class="table">

| 

```cpp
new
```

 | 

```cpp
malloc()
```

 |
| Call constructor | Do not call the constructor. |
| It is an operator. | It is a function. |
| Returns the exact data type. | Return void *. |

</figure>

如果你在上面的帖子中发现任何不正确的地方，或者你想分享更多关于上面讨论的主题的信息，请写评论。