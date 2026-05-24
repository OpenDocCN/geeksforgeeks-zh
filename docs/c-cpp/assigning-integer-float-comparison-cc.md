# 在 C/C++

中给浮点和比较赋值一个整数

> 原文:[https://www . geesforgeks . org/assignment-integer-float-comparison-cc/](https://www.geeksforgeeks.org/assigning-integer-float-comparison-cc/)

考虑下面的 C++ 程序并预测输出。

```cpp
#include <iostream>
using namespace std;

int main()
{
    float f = 0xffffffff;
    unsigned int x = 0xffffffff; // Value 4294967295
    if (f == x) 
        cout << "true";
    else 
        cout << "false";
    return 0;
}
```

如果编译器使用“ [IEEE754 32 位单浮点类型](https://www.geeksforgeeks.org/floating-point-representation-basics/)，则上述程序的输出为**假**。如果我们定义:

```cpp
float f = 0xffffffff;
```

我们基本上是试图将一个 32 位整数(有符号或无符号)赋给一个 32 位浮点数。编译器会首先将整数 0xffffffff 转换为最近的 32 位浮点，浮点的内存表示 **f** 与整数 0xffffffff 不同。通过打印 f 和 x

```cpp
#include <iostream>
using namespace std;

int main()
{
    float f = 0xffffffff;
    unsigned int x = 0xffffffff; 
    cout << "f = " << f << endl;
    cout << "x = " << x << endl;
    return 0;
}
```

，我们可以看到上面的数值

输出:

```cpp
f = 4.29497e+09
x = 4294967295

```

例如，即使我们直接复制内存，我们也有一个整数(值等于 0xffffffff)，我们复制内容(内存值)。由于 IEEE754 中的 0xffffffff 不是一个有效的浮点数，所以如果将这个无效的表示与其本身进行比较，它就不相等。

```cpp
unsigned int x = 0xffffffff;
memoryCopy(&f, &x, sizeof(x));
```

本文由**里沙夫·拉吉**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。