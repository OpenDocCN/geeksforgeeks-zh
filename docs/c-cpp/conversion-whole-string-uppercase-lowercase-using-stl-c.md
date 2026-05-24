# 在 C++ 中使用 STL 将整个字符串转换为大写或小写

> 原文:[https://www . geesforgeks . org/conversion-整串-大写-小写-using-stl-c/](https://www.geeksforgeeks.org/conversion-whole-string-uppercase-lowercase-using-stl-c/)

给定一个字符串，在 C++ 中使用 STL 将整个字符串转换为大写或小写。

示例:

```cpp
For uppercase conversion
Input : s = "String"
Output : s = "STRING"

For lowercase conversion
Input : s = "String"
Output : s = "string"

```

使用的函数:
[变换](https://www.geeksforgeeks.org/transform-c-stl-perform-operation-elements/):对给定的数组/字符串执行变换。
**toupper(int c) :** 返回字符 c 的大写版本，如果 c 已经大写，则返回 c 本身。
**tolower(int c) :** 返回字符 c 的小写版本，如果 c 已经是小写，则返回 c 本身。

```cpp
// C++ program to convert whole string to
// uppercase or lowercase using STL.
#include<bits/stdc++.h>
using namespace std;

int main()
{
    // su is the string which is converted to uppercase
    string su = "Jatin Goyal";

    // using transform() function and ::toupper in STL
    transform(su.begin(), su.end(), su.begin(), ::toupper);
    cout << su << endl;

    // sl is the string which is converted to lowercase
    string sl = "Jatin Goyal";

    // using transform() function and ::tolower in STL
    transform(sl.begin(), sl.end(), sl.begin(), ::tolower);
    cout << sl << endl;

    return 0;
}
```

输出:

```cpp
JATIN GOYAL
jatin goyal

```

本文由 **Jatin Goyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。