# c++ 中的 div()函数

> 原文:[https://www.geeksforgeeks.org/div-function-c/](https://www.geeksforgeeks.org/div-function-c/)

给定分子和分母，我们必须在不使用模或除运算符的情况下找到它们的商和余数。div()函数允许我们轻松高效地完成相同的任务。

**div()函数:**以 div_t、ldiv_t 或 lldiv_t 类型的结构返回数除以 denom ( number/denom)的整数商和余数，该结构有两个成员:quot 和 rem。

**语法:**

```cpp
div_t div(int numerator, int denominator);
ldiv_t div(long numerator, long denominator);
lldiv_t div(long long numerator, long long denominator);
```

当我们使用 div()函数时，它返回一个包含参数的商和余数的结构。div()函数中传递的第一个参数作为分子，第二个参数作为分母。

对于 int 值，返回的结构是 div_t。

## C++

```cpp
typedef struct
    {
    int quot; /* Quotient.  */
    int rem; /* Remainder.  */
} div_t;
```

同样，对于长值，返回结构 ldiv_t，对于长值，返回结构 lldiv_t。

## C++

```cpp
ldiv_t:
struct ldiv_t {
    long quot;
    long rem;
};

lldiv_t:
struct lldiv_t {
    long long quot;
    long long rem;
};
```

**在哪里有用？**

问题是，既然我们都有%和/运算符，为什么还要用 div()函数呢？。在一个同时需要商和余数的程序中，使用 div()函数是最好的选择，因为它可以同时为您计算两个值，此外，与逐个使用%和/函数相比，它需要更少的时间。
使用 div()函数时，*使用%运算符和使用 div()都将返回相同的余数值，也就是说，如果我们使用%运算符得到的余数为负值，那么我们也将使用 div()函数得到负值的余数。例如，div(-40，3)将给出“-1”的余数。*。因此，div()函数可以根据自己的需要有效地使用。

**分母为 0 时会发生什么？**

如果这个函数的任何一个部分，即余数或商不能被表示或不能找到结果，那么整个结构显示出一个**未定义的行为**。

**注意:**在使用 div()函数时，请记住在程序中包含 cstdlib.h 库。

示例:

```cpp
Input : div(40, 5)
Output :quot = 8 rem = 0

Input :div(53, 8)
Output :quot = 6 rem = 5

Input : div(-40,3)
Output : quot = -13 , rem = -1
```

**实施:**

## C++

```cpp
// CPP program to illustrate
// div() function
#include <iostream>
#include <cstdlib>
using namespace std;

int main()
{
    div_t result1 = div(100, 6);

    cout << "Quotient of 100/6 = " <<
                      result1.quot << endl;
    cout << "Remainder of 100/6 = " <<
                       result1.rem << endl;

    ldiv_t result2 = div(19237012L,251L);

    cout << "Quotient of 19237012L/251L = " <<
                          result2.quot << endl;
    cout << "Remainder of 19237012L/251L = " <<
                            result2.rem << endl;

    return 0;
}
```

**输出:**

```cpp
Quotient of 100/6 = 16
Remainder of 100/6 = 4
Quotient of 19237012L/251L = 76641
Remainder of 19237012L/251L = 121
```

本文由 **Ayush Saxena** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。