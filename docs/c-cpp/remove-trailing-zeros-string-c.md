# 在 C++ 中删除字符串的尾随零

> 原文:[https://www . geesforgeks . org/remove-尾随-零-string-c/](https://www.geeksforgeeks.org/remove-trailing-zeros-string-c/)

给定一串数字，去掉尾随的零。

示例:

```cpp
Input : 00000123569
Output : 123569

Input : 000012356090
Output : 12356090

```

1)计算尾随零。
2)使用[字符串擦除功能](https://www.geeksforgeeks.org/c-string-class-and-its-applications/)删除等于以上计数的字符。

下面是 C++ 实现。

```cpp
// C++ program to remove trailing/preceding zeros
// from a given string
#include<iostream>
using namespace std;

string removeZero(string str)
{
    // Count trailing zeros
    int i = 0;
    while (str[i] == '0')
       i++ ;

    // The erase function removes i characters
    // from given index (0 here)
    str.erase(0, i);

    return str;
}

// Driver code
int main()
{
    string str;
    str = "00000123569";
    str = removeZero(str);
    cout << str << endl;
    return 0;
}
```

输出:

```cpp
123569
```

本文由 [**普拉哈尔·阿格沃尔**](http://prakhar.info) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。