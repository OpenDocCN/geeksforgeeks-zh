# 标准::C++ 中的 mem chr

> 原文:[https://www.geeksforgeeks.org/stdmemchr-in-cpp/](https://www.geeksforgeeks.org/stdmemchr-in-cpp/)

C++ 提供了各种要使用的标准模板库。其中一个是 memchr()函数，它将在指定数量的字符中搜索第一个出现的字符。
**模板**

```cpp
const void* memchr( const void* ptr, int ch, std::size_t count );
Parameters : 
ptr : Pointer to the object to be searched for.
ch : Character to search for.
count : Number of character to be searched for.

Return value:
If the character is found, the memchr() function returns a pointer to 
the location of the character, otherwise returns null pointer.

```

```cpp
// CPP program to illustrate memchr()
#include <cstring>
#include <iostream>

using namespace std;

int main()
{
    char sr[] = "This is a sample";
    char ch = 's';
    int count = 13;

    if (memchr(sr, ch, count))
        cout << ch << " is present in first "
             << count << " characters of \"" << sr << "\"";
    else
        cout << ch << " is not present in first "
             << count << " characters of \"" << sr << "\"";

    return 0;
}
```

输出:

```cpp
s is present in first 13 characters of "This is a sample"

```

示例:

```cpp
// CPP program to illustrate memchr()
#include <iostream>
#include <cstring>

int main()
{
    char arr[] = { 'b', 'a', 'd', 'e', 'f', 'A', 'g' };
    char* pc = (char*)std::memchr(arr, 'g', sizeof arr);
    if (pc != NULL)
        std::cout << "search character found\n";
    else
        std::cout << "search character not found\n";
}
```

输出:

```cpp
search character found

```

本文由**普拉纳夫**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。