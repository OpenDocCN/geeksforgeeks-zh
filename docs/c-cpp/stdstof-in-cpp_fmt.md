# 标准::C++ 中的 stof

> 原文:[https://www.geeksforgeeks.org/stdstof-in-cpp/](https://www.geeksforgeeks.org/stdstof-in-cpp/)

解析字符串，将其内容解释为浮点数，浮点数作为 `float` 类型的值返回。

## 语法

```cpp
float stof (const string&  str, size_t* idx = 0);
float stof (const wstring& str, size_t* idx = 0);
```

## 参数

- `str`：包含浮点数表示的字符串对象。
- `idx`：指向 `size_t` 类型对象的指针，函数会将该对象的值设置为 `str` 中数值之后的下一个字符的位置。此参数也可以是一个空指针，在这种情况下它不会被使用。

## 返回值

成功时，函数返回转换后的浮点数，其值为 `float` 类型。

## 示例

下面是 `std::stof` 的 C++ 实现：

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

输出：

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

输出：

```cpp
1000
```

本文由 **Rohit Thapliyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。