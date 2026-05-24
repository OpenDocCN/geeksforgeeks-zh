# c++ 中的 STD::memcmp()

> 原文:[https://www.geeksforgeeks.org/stdmemcmp-in-cpp/](https://www.geeksforgeeks.org/stdmemcmp-in-cpp/)

它比较 buf1 和 buf2 指向的数组的第一个计数字符。
语法:

```cpp
int memcmp(const void *buf1, const void *buf2, size_t count);
Return Value: it returns an integer.
Parameters:  
buf1 : Pointer to block of memory.
buf2 : Pointer to block of memory.
count : Maximum numbers of bytes to compare.
Return Value is interpreted as :
Value                                Meaning
Less than zero                       buf1 is less than buf2.
Zero                                 buf1 is equal to buf2.
Greater than zero                    buf1 is greater than buf2.

```

**实施例 1。当计数大于零时(> 0)**

```cpp
// CPP program to illustrate std::memcmp()
#include <iostream>
#include <cstring>

int main()
{
    char buff1[] = "Welcome to GeeksforGeeks";
    char buff2[] = "Hello Geeks ";

    int a;

    a = std::memcmp(buff1, buff2, sizeof(buff1));

    if (a > 0)
        std::cout << buff1 << " is greater than " << buff2;
    else if (a < 0)
        std::cout << buff1 << "is less than " << buff2;
    else
        std::cout << buff1 << " is the same as " << buff2;

    return 0;
}
```

输出:

```cpp
Welcome to GeeksforGeeks is greater than Hello Geeks 

```

**例 2。当计数小于零时(< 0)**

```cpp
// CPP program to illustrate std::memcmp() 
#include <cstring>
#include <iostream>

int main()
{
    int comp = memcmp("GEEKSFORGEEKS", "geeksforgeeks", 6);
    if (comp == 0) {
        std::cout << "both are equal";
    }
    if (comp < 0) {
        std::cout << "String 1  is less than String 2";
    } else {
        std::cout << "String 1 is  greater than String 2";
    }
}
```

输出:

```cpp
String 1 is less than String 2

```

**例 3:当计数等于零时(= 0)**

```cpp
// CPP program to illustrate std::memcmp()
#include <iostream>
#include <cstring>

int main()
{
    char buff1[] = "Welcome to GeeksforGeeks";
    char buff2[] = "Welcome to GeeksforGeeks";

    int a;

    a = std::memcmp(buff1, buff2, sizeof(buff1));

    if (a > 0)
        std::cout << buff1 << " is greater than " << buff2;
    else if (a < 0)
        std::cout << buff1 << "is less than " << buff2;
    else
        std::cout << buff1 << " is the same as " << buff2;

    return 0;
}
```

输出:

```cpp
Welcome to GeeksforGeeks is the same as Welcome to GeeksforGeeks

```

本文由**Shivani ghishial**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。