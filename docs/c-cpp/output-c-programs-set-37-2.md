# c++ 程序输出|第 37 集

> 原文:[https://www.geeksforgeeks.org/output-c-programs-set-37-2/](https://www.geeksforgeeks.org/output-c-programs-set-37-2/)

预测以下 C++ 代码的输出:

**问题 1**

```cpp
#include <iostream>
int main()
{
    if (std::cout << "hello")
        std::cout << " world";
    else
        std::cout << " else part";

    return 0;
}
```

输出:hello world
说明:由于**STD::cout<<“hello”**返回对 **std::cout** 的引用，因此条件变为真，执行 if 块。

**问题 2**

```cpp
#include <iostream>
int main()
{
    if (2)
        std::cout << "hello";
    else
        std::cout << "world";
    return 0;
}
```

输出:你好
说明:由于 **2** 为非零(即真)，因此条件为真，执行 if 块。

**问题 3**

```cpp
#include <iostream>
int main()
{
    if (0)
        std::cout << "hello";
    else
        std::cout << "world";
    return 0;
}
```

输出:世界

描述:由于 0 相当于 false(在这个问题中)，因此条件为 false，执行 else 块。

**问题 4**

```cpp
#include <iostream>
int main()
{
    if (NULL)
        std::cout << "hello";
    else
        std::cout << "world";
    return 0;
}
```

输出:世界

描述:由于空值等于 0，即假(在这个特殊问题中)，因此条件为假，执行 else 块。

**问题 5**

```cpp
#include <iostream>
int main()
{
    int n;

    if (std::cin >> n) {
        std::cout << "hello";
    } else
        std::cout << "world";
    return 0;
}
```

输入:100
输出:你好
说明:由于 **std::cin > >【你好】**返回对 **std::cin** 的引用，因此条件为真，执行 if 块。

输入:[无]
输出:世界

描述:由于没有提供输入，条件变为假，因此执行 else 块。

本文由 **Palak Jain** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。