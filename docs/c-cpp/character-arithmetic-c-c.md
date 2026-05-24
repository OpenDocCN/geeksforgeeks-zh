# C 和 C++ 中的字符算术

> 原文:[https://www.geeksforgeeks.org/character-arithmetic-c-c/](https://www.geeksforgeeks.org/character-arithmetic-c-c/)

众所周知，字符范围在-128 到 127 或 0 到 255 之间。做字符运算时，这一点必须牢记在心。为了更好地理解，让我们举个例子。

## C

```cpp
// C program to demonstrate character arithmetic.
#include <stdio.h>

int main()
{
    char ch1 = 125, ch2 = 10;
    ch1 = ch1 + ch2;
    printf("%d\n", ch1);
    printf("%c\n", ch1 - ch2 - 4);
    return 0;
}
```

**输出:**

```cpp
-121
y
```

所以%d 说明符导致一个整数值被打印，而%c 说明符导致一个字符值被打印。但是必须注意，在使用%c 说明符时，整数值不应超过 127。
到目前为止还不错。
但是对于 c++ 来说，结果有点不同。

看这个例子更好理解。

## C++

```cpp
// A C++ program to demonstrate character
// arithmetic in C++.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    char ch = 65;
    cout << ch << endl;
    cout << ch + 0 << endl;
    cout << char(ch + 32) << endl;
    return 0;
}
```

**输出:**

```cpp
A
65
a
```

如果没有“+”运算符，将打印字符值。但是当与‘+’运算符一起使用时，表现就不同了。使用“+”运算符隐式地将其类型转换为“int”。因此，总结一下，在字符算法中，将 char 变量类型转换为“char”是显式的，而转换为“int”是隐式的。

本文由 [**帕维恩·库马尔**](https://auth.geeksforgeeks.org/profile.php) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。