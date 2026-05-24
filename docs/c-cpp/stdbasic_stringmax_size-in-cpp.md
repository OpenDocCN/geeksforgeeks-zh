# std::basic_string::max_size 在 C++ 中

> 原文:[https://www . geesforgeks . org/stdbasic _ stringmax _ size-in-CPP/](https://www.geeksforgeeks.org/stdbasic_stringmax_size-in-cpp/)

std::basic_string::max_size 用于计算由于系统或库实现限制，字符串能够容纳的最大元素数。

```cpp
size_type max_size() const;
Parameters : None
Return value : Maximum number of characters
Exceptions : None
```

```cpp
// CPP program to compute the limit of a string
// using max_size
#include <iostream>
#include <string>

int main()
{
    std::string str;

    // Calling max_size()
    std::cout << "Maximum size of a string is " << str.max_size() << std :: endl;
} 
```

输出:

```cpp
Maximum size of a string is 4294967294

```

**注意:**最大大小可以根据编译器和系统而定。

本文由 **Rohit Thapliyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。