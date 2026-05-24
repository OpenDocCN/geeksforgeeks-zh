# 不使用算术、关系或条件运算符设置变量

> 原文:[https://www . geesforgeks . org/set-variable-not-use-算术-关系-条件-运算符/](https://www.geeksforgeeks.org/set-variable-without-using-arithmetic-relational-conditional-operator/)

给定三个整数 a、b 和 c，其中 c 可以是 0 或 1。在不使用任何算术运算的情况下，关系运算符和条件运算符根据以下规则设置变量 x 的值–

```cpp
If c = 0
    x = a
Else // Note c is binary
    x = b.

```

示例:

```cpp
Input: a = 5, b = 10, c = 0;
Output: x = 5

Input: a = 5, b = 10, c = 1;
Output: x = 10

```

**解决方案 1:** 使用算术运算符
如果允许我们使用算术运算符，我们可以使用以下任一表达式轻松计算 x–

```cpp
x = ((1 - c) * a) + (c * b)

OR

x = (a + b) - (!c * b) - (c * a);

OR

x = (a * !c) | (b * c);

```

```cpp
#include <iostream>
using namespace std;

int calculate(int a, int b, int c)
{
    return ((1 - c) * a) + (c * b); 
}

int main()
{
   int a = 5, b = 10, c = 0;

   int x = calculate(a, b, c);
   cout << x << endl;

   return 0;
}
```

输出:

```cpp
5

```

**解 2:** 不使用算术运算符
的思想是构造一个大小为 2 的数组，这样数组的索引 0 存储变量‘a’的值，索引 1 存储变量 b 的值。现在我们根据变量 c 的值在数组的索引 0 或索引 1 返回值

```cpp
#include <iostream>
using namespace std;

int calculate(int a, int b, int c)
{
   int arr[] = {a, b};
   return *(arr + c);
}

int main()
{
   int a = 5, b = 10, c = 1;

   int x = calculate(a, b, c);
   cout << x << endl;

   return 0;
}
```

输出:

```cpp
10

```

本文由**阿迪蒂亚·戈尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。