# c++ 中的 STD::to _ string

> 原文:[https://www.geeksforgeeks.org/stdto_string-in-cpp/](https://www.geeksforgeeks.org/stdto_string-in-cpp/)

将数值转换为字符串

**语法:**

```cpp
string to_string (int val);
string to_string (long val);
string to_string (long long val);
string to_string (unsigned val);
string to_string (unsigned long val);
string to_string (unsigned long long val);
string to_string (float val);
string to_string (double val);
string to_string (long double val);

Parameters :
val - Numerical value.

Return Value :
A string object containing the representation of val as a sequence of characters.

```

```cpp
// CPP program to illustrate
// std::to_string
#include <bits/stdc++.h>

// Driver code
int main()
{

    // Converting float to string
    std::string str1 = std::to_string(12.10);

    // Converting integer to string
    std::string str2 = std::to_string(9999);

    // Printing the strings
    std::cout << str1 << '\n';
    std::cout << str2 << '\n';
    return 0;
}
```

输出:

```cpp
12.100000
9999

```

**问题:**求给定整数中的特定数字。
例:

```cpp
Input : number  = 10340, digit = 3
Output : 3 is at position 3

```

```cpp
// CPP code to find a digit in a number
// using std::tostring
#include <bits/stdc++.h>

// Driver code
int main()
{

    // Converting number to string
    std::string str = std::to_string(9954);

    // Finding 5 in the number
    std::cout << "5 is at position " << str.find('5') + 1;
}
```

输出:

```cpp
5 is at position 3

```

本文由 **Rohit Thapliyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。