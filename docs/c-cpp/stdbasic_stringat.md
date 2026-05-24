# STD::basic _ string::at in c++

> 哎哎哎:# t0]https://www . geeksforgeeks . org/stdbasic _ string at/

返回对指定位置位置的字符的引用。该函数自动检查 pos 是否是字符串中字符的有效位置(即 pos 是否小于字符串长度)，如果不是，则抛出一个 out_of_range 异常。

**语法:**

```cpp
reference at (size_type pos);
const_reference at (size_type pos) const;
Parameters :
pos - position of the character to return
Return value :
Reference to the requested character
Exceptions :
Throws std::out_of_range if pos >= size().
```

```cpp
// CPP program to access a character through
// std::basic_string::at 
#include <stdexcept>
#include <iostream>

int main()
{
    // String with valid indices from 0 to 2
    std::string str = "abc";

    // Printing size of string
    std::cout << "string size = " << str.size() << '\n';

    // Accessing out of bounds index
    try 
    {
        str.at(4) = 't';
    }

    // If error is generated, it is caught
    catch (std::out_of_range const& error) 
    {
        std::cout << error.what() << '\n';
    }
}
```

输出:

```cpp
string size = 3
basic_string::at: __n (which is 4) >= this->size() (which is 3)

```

本文由 **[罗希特·塔普利亚尔](https://www.linkedin.com/in/rohit-thapliyal-515b5913a/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。