# STD::basic _ string::c++ 中的运算符[]

> 原文:[https://www.geeksforgeeks.org/stdbasic_stringoperator-in-c/](https://www.geeksforgeeks.org/stdbasic_stringoperator-in-c/)

返回对指定位置的字符的引用。不执行边界检查。如果 pos > size()，则行为未定义。

**语法:**

```cpp
reference operator[] (size_type pos);
const_reference operator[] (size_type pos) const;
Parameters :
pos - position of the character to return
Return value :
Reference to the requested character
Exceptions :
No exception is thrown

```

```cpp
/* CPP program to access
   a character through
   std::basic_string::operator[] */
#include <iostream>

//Driver code
int main()
{
    //String with valid indices from 0 to 2
    std::string str = "abc";

    //Printing size of string
    std::cout << "string size = " << str.size() << '\n';

    //Accessing element at index 2
    std::cout << "Element : " << str[2];
}
```

输出

```cpp
string size = 3
Element : c

```

本文由 **[罗希特·塔普利亚尔](https://www.linkedin.com/in/rohit-thapliyal-515b5913a/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。