# 标准::C++ 中的 stof

> 原文:[https://www.geeksforgeeks.org/stdstof-in-cpp/](https://www.geeksforgeeks.org/stdstof-in-cpp/)

解析字符串，将其内容解释为浮点数，浮点数作为 float 类型的值返回。

**语法:**

```cpp
float stof (const string&  str, size_t* idx = 0);
float stof (const wstring& str, size_t* idx = 0);

Parameters :
str : String object with the representation of a floating-point number.
idx : Pointer to an object of type size_t, whose value is set by the function
to position of the next character in str after the numerical value.
This parameter can also be a null pointer, in which case it is not used.

Return Value :
On success, the function returns the converted floating-point number as a value of type float.

```

下面是 std::stof :

```cpp
// CPP code to convert floating 
// type number to string
#include <bits/stdc++.h>

int main()
{
    // String to be parsed
    std::string str = "100.80";

    // val to store parsed floating type number
    float val = std::stof(str);

    // Printing parsed floating type number
    std::cout << val;

    return 0;
}
```

的 C++ 实现

输出:

```cpp
100.8
```

```cpp
// CPP code to convert integer 
// type number to string
#include <bits/stdc++.h>

int main()
{
    // String to be parsed
    std::string str = "1000";

    // val to store parsed integer type number
    float val = std::stof(str);

    // Printing parsed integer type number
    std::cout << val;

    return 0;
}
```

输出:

```cpp
1000
```

本文由 **Rohit Thapliyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。