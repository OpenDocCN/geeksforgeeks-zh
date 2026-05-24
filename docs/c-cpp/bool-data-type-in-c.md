# c++ 中的 Bool 数据类型

> 原文:[https://www.geeksforgeeks.org/bool-data-type-in-c/](https://www.geeksforgeeks.org/bool-data-type-in-c/)

ISO/ANSI C++ 标准在最初的 C++ 规范中增加了某些新的数据类型。提供它们是为了在某些情况下提供更好的控制，也是为了给 C++ 程序员提供便利。
新的数据类型之一是: **bool**
**语法:**

```cpp
bool b1 = true;      // declaring a boolean variable with true value   
```

在 C++ 中，数据类型 bool 被引入来保存布尔值，*真*或*假*。值*真*或*假*在 C++ 语言中被添加为关键字。
**要点:**

*   *真*默认数值为 1，*假*默认数值为 0。
*   We can use bool type variables or values *true* and *false* in mathematical expressions also.For instance,

    ```cpp
    int x = false + true + 6;
    ```

    是有效的，右边的表达式将评估为 **7** 为*假*值为 0，*真*值为 1。

*   也可以将数据类型整数或浮点值隐式转换为 bool 类型。例如，语句-

    ```cpp
    bool x = 0;  // false
    bool y = 100;  // true
    bool z = 15.75;  // true
    ```

```cpp
// CPP program to illustrate bool 
// data type in C++
#include<iostream>
using namespace std;
int main()
{
    int x1 = 10, x2 = 20, m = 2;
    bool b1, b2;
    b1 = x1 == x2; // false

    b2 = x1 < x2; // true

    cout << "b1 is = " << b1 << "\n";
    cout << "b2 is = " << b2 << "\n";
    bool b3 = true;

    if (b3)
        cout << "Yes" << "\n";
    else
        cout << "No" << "\n";

    int x3 = false + 5 * m - b3;
    cout << x3;

return 0;

}
```

输出:

```cpp
b1 is = 0
b2 is = 1
Yes
9

```

**相关文章:** [如何在 C 语言中使用 Bool？](https://www.geeksforgeeks.org/bool-in-c/)

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。