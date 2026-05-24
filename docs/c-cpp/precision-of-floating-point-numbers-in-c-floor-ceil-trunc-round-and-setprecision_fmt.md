# C++ 中浮点数的精度（`floor()`、`ceil()`、`trunc()`、`round()` 和 `setprecision()`）

> 原文：[https://www.geeksforgeeks.org/precision-of-floating-point-numbers-in-c-floor-ceil-trunc-round-and-setprecision/](https://www.geeksforgeeks.org/precision-of-floating-point-numbers-in-c-floor-ceil-trunc-round-and-setprecision/)

1/3 的十进制等效值是 0.333...。无限长的数字需要无限的内存来存储，而我们通常只有 4 或 8 个字节。因此，浮点数只存储一定数量的有效数字，其余的都丢失了。浮点数的**精度**定义了在不丢失信息的情况下，它可以表示多少有效数字。输出浮点数时，`cout` 的默认精度为 6，它会截断其后的任何内容。

下面给出了一些用于为 C++ 中的浮点数提供精度的库和方法：

## `floor()`

`floor()` 将给定值向下舍入到最接近的小于给定值的整数。

```cpp
// C++ program to demonstrate working of floor()
// in C/C++
#include<bits/stdc++.h>
using namespace std;

int main()
{
    double x =1.411, y =1.500, z =1.711;
    cout << floor(x) << endl;
    cout << floor(y) << endl;
    cout << floor(z) << endl;

    double a =-1.411, b =-1.500, c =-1.611;
    cout << floor(a) << endl;
    cout << floor(b) << endl;
    cout << floor(c) << endl;
    return 0;
}
```

输出：

```cpp

```

## `ceil()`

`ceil()` 将给定值向上舍入到最接近的大于给定值的整数。

```cpp
// C++ program to demonstrate working of ceil()
// in C/C++
#include<bits/stdc++.h>
using namespace std;

int main()
{
    double x = 1.411, y = 1.500, z = 1.611;
    cout << ceil(x) << endl;
    cout << ceil(y) << endl;
    cout << ceil(z) << endl;

    double a = -1.411, b = -1.500, c = -1.611;
    cout << ceil(a) << endl;
    cout << ceil(b) << endl;
    cout << ceil(c) << endl;
    return 0;
}
```

输出：

```cpp

```

## `trunc()`

`trunc()` 移除小数点后的数字。

```cpp
// C++ program to demonstrate working of trunc()
// in C/C++
#include<bits/stdc++.h>
using namespace std;

int main()
{
    double x = 1.411, y = 1.500, z = 1.611;
    cout << trunc(x) << endl;
    cout << trunc(y) << endl;
    cout << trunc(z) <<endl;

    double a = -1.411, b = -1.500, c = -1.611;
    cout << trunc(a) <<endl;
    cout << trunc(b) <<endl;
    cout << trunc(c) <<endl;
    return 0;
}
```

输出：

```cpp

```

## `round()`

将给定数字四舍五入到最接近的整数。

```cpp
// C++ program to demonstrate working of round()
// in C/C++
#include<bits/stdc++.h>
using namespace std;

int main()
{
    double x = 1.411, y = 1.500, z = 1.611;

    cout << round(x) << endl;
    cout << round(y) << endl;
    cout << round(z) << endl;

    double a = -1.411, b = -1.500, c = -1.611;
    cout << round(a) << endl;
    cout << round(b) << endl;
    cout << round(c) << endl;
    return 0;
}
```

输出：

```cpp

```

## `setprecision()`

`setprecision()` 与 `fixed` 一起使用时，可以为浮点数提供小数点后指定的精度。

```cpp
// C++ program to demonstrate working of setprecision()
// in C/C++
#include<bits/stdc++.h>
using namespace std;

int main()
{
    double pi = 3.14159, npi = -3.14159;
    cout << fixed << setprecision(0) << pi <<" "<<npi<<endl;
    cout << fixed << setprecision(1) << pi <<" "<<npi<<endl;
    cout << fixed << setprecision(2) << pi <<" "<<npi<<endl;
    cout << fixed << setprecision(3) << pi <<" "<<npi<<endl;
    cout << fixed << setprecision(4) << pi <<" "<<npi<<endl;
    cout << fixed << setprecision(5) << pi <<" "<<npi<<endl;
    cout << fixed << setprecision(6) << pi <<" "<<npi<<endl;
}
```

输出：

```cpp
3 -3
3.1 -3.1
3.14 -3.14
3.142 -3.142
3.1416 -3.1416
3.14159 -3.14159
3.141590 -3.141590
```

**注意：** 当 `setprecision()` 中提到的值超过原始数字中的浮点位数时，浮点数字后会附加 0，以匹配用户提到的精度。

还有其他方法可以为浮点数提供精度。上面提到的是在竞争性编码过程中为浮点数提供精度的几种最常用的方法。

本文由 **[阿迪蒂亚·古普塔](https://practice.geeksforgeeks.org/user-profile.php?user=Aditya%20Gupta%204)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。