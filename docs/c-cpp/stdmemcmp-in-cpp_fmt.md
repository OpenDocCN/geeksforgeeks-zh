# C++ 中的 `std::memcmp()`

> 原文: [https://www.geeksforgeeks.org/stdmemcmp-in-cpp/](https://www.geeksforgeeks.org/stdmemcmp-in-cpp/)

它比较 `buf1` 和 `buf2` 指向的数组的第一个 `count` 字符。

## 语法

```cpp
int memcmp(const void *buf1, const void *buf2, size_t count);
```

**返回值**：它返回一个整数。

**参数**：
- `buf1`：指向内存块的指针。
- `buf2`：指向内存块的指针。
- `count`：要比较的最大字节数。

**返回值解释**：
| 值 | 含义 |
| :--- | :--- |
| 小于零 | `buf1` 小于 `buf2`。 |
| 零 | `buf1` 等于 `buf2`。 |
| 大于零 | `buf1` 大于 `buf2`。 |

## 示例 1：当 `count` 大于零时 (`> 0`)

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

输出：

```cpp
Welcome to GeeksforGeeks is greater than Hello Geeks
```

## 示例 2：当 `count` 小于零时 (`< 0`)

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
        std::cout << "String 1  is less than String 2";
    } else {
        std::cout << "String 1 is  greater than String 2";
    }
}
```

输出：

```cpp
String 1 is less than String 2
```

## 示例 3：当 `count` 等于零时 (`= 0`)

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

输出：

```cpp
Welcome to GeeksforGeeks is the same as Welcome to GeeksforGeeks
```

本文由 **Shivani ghishial** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。