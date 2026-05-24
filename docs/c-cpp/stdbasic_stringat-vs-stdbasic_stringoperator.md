# STD::basic _ string::at vs STD::basic _ string::operator[]

> 原文:[https://www . geesforgeks . org/stdbasic _ string gat-vs-stdbasic _ string operator/](https://www.geeksforgeeks.org/stdbasic_stringat-vs-stdbasic_stringoperator/)

[std::basic_string::at](https://www.geeksforgeeks.org/stdbasic_stringat/) 、[STD::basic _ string::operator[]](https://www.geeksforgeeks.org/stdbasic_stringoperator-in-c/)
at()和 operator[]都可以用来访问字符串中的元素。但是当 pos > =size 时，两者在如何处理异常情况上有一点不同。

*   std::basic_string::at 抛出 **std::超出范围**如果 **pos > = size()** 。
*   std::bsic_string::operator[]抛出**无异常**并产生**未定义结果**。

下面是 C++ 实现，显示了 STD::basic _ string::at–
的异常处理属性

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ implementation of std::basic_string::at
#include <stdexcept>
#include <iostream>

int main()
{
    // Length = 13\. Valid indices are from '0' to '12'
    std::string str = "Geeksforgeeks";

    // Accessing an out of bounds
    try
    {
        // Throwing an out_of_range exception
        std::cout << str.at(13) << "\n";
    }

    // Error caught
    catch (std::out_of_range const& error)
    {
        std::cout << "Exception caught" << "\n";

        // Printing the type of exception
        std::cout << error.what() << "\n";
    }
}
```

输出:

```cpp
Exception caught
basic_string::at: __n (which is 13) >= this->size() (which is 13)
```

下面是 C++ 实现，显示了 STD::basic _ string::operator[]–
中的无边界检查

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ implementation of std::basic_string::operator[]
#include <stdexcept>
#include <iostream>

int main()
{
    // Length = 13\. Valid indices are from '0' to '12'
    std::string str = "Geeksforgeeks";

    // Accessing an out of bounds
    try
    {
        //Throwing an out_of_range exception
        std::cout << str[13] << "\n";
    }

    // Error caught
    catch (std::out_of_range const& error)
    {
        std::cout << "Exception caught" << "\n";
        // Printing the type of exception
        std::cout << error.what() << "\n";
    }
}
```

输出:

```cpp
Undefined result
```

本文由 **Rohit Thapliyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。