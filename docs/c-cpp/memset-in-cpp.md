# c++ 中的 Memset

> 原文:[https://www.geeksforgeeks.org/memset-in-cpp/](https://www.geeksforgeeks.org/memset-in-cpp/)

Memset()是一个 C++ 函数。它将单个字符复制指定的次数到一个对象。在**<>**头文件中定义。

**语法:**

```cpp
void* memset( void* str, int ch, size_t n);
```

**Memset()** 将值 ch 转换为无符号字符，并将其复制到 str[]指向的对象的前 n 个字符中。如果对象不是普通可复制的(例如，标量、数组或 C 兼容结构)，则行为是未定义的。如果 n 大于 str 指向的对象的大小，则行为未定义。

**参数:**

*   **str[] :** 指向要复制字符的对象的指针。
*   **ch :** 要复制的角色。
*   **n :** 要复制的字节数。

**返回值:**memset()函数返回字符串，即指向目标字符串的指针。

## CPP

```cpp
// CPP program to demonstrate memset
#include <cstring>
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    char str[] = "geeksforgeeks";
    memset(str, 't', sizeof(str));
    cout << str;
    return 0;
}
```

**输出**

```cpp
tttttttttttttt
```

> **注意:**我们也可以使用 memset()将整型数据类型的所有值设置为 0 或-1。如果我们用它来设置为其他值，它将不起作用。原因很简单，memset 是逐字节工作的。

## CPP

```cpp
// CPP Program to demonstrate that we can use memset() to
// set all values as 0 or -1 for integral data types also
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    int a[5];

    // all elements of A are zero
    memset(a, 0, sizeof(a));
    for (int i = 0; i < 5; i++)
        cout << a[i] << " ";
    cout << endl;

    // all elements of A are -1
    memset(a, -1, sizeof(a));
    for (int i = 0; i < 5; i++)
        cout << a[i] << " ";
    cout << endl;

    // Would not work
    memset(a, 5, sizeof(a)); // WRONG
    for (int i = 0; i < 5; i++)
        cout << a[i] << " ";
}
```

**输出**

```cpp
0 0 0 0 0 
-1 -1 -1 -1 -1 
84215045 84215045 84215045 84215045 84215045 
```

**另请参阅:**

*   [memcpy()哦，天啊 c/c++ ](https://www.geeksforgeeks.org/memcpy-in-cc/)
*   [memcmp()哦，天啊 c++ ](https://www.geeksforgeeks.org/stdmemcmp-in-cpp/)

本文由**普拉纳夫**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。