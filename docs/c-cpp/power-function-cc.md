# C/c++

中的幂函数

> 原文:[https://www.geeksforgeeks.org/power-function-cc/](https://www.geeksforgeeks.org/power-function-cc/)

给定两个基数和指数，pow()函数找到 x 的 y 次方，即 x <sup>y</sup> 。基本上在 C 中，指数值是用幂()函数计算的。pow()是获取一个数的幂的函数，但是我们必须在 c/c++ 中使用#include < math.h >才能使用那个 pow()函数。然后传递两个数字。示例–pow(4，2)；然后我们将得到 4^2 的结果，这是 16。
**例:**

```cpp
Input: 2.0, 5.0
Output: 32
Explanation: 
pow(2.0, 5.0) executes 2.0 raised to
the power 5.0, which equals 32

Input: 5.0, 2.0
Output: 25
Explanation: 
pow(5.0, 2.0) executes 5.0 raised to
the power 2.0, which equals 25
```

**语法:**

```cpp
double pow(double x, double y);
```

**参数:**该方法采用两个参数:

*   **x :** 浮点基值
*   **y :** 浮点功率值

**节目:**

## C

```cpp
// C program to illustrate
// power function
#include <math.h>
#include <stdio.h>

int main()
{
    double x = 6.1, y = 4.8;

    // Storing the answer in result.
    double result = pow(x, y);
    printf("%.2lf", result);

    return 0;
}
```

## C++

```cpp
// CPP program to illustrate
// power function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    double x = 6.1, y = 4.8;

    // Storing the answer in result.
    double result = pow(x, y);

    // printing the result upto 2
    // decimal place
    cout << fixed << setprecision(2) << result << endl;

    return 0;
}
```

**Output:** 

```cpp
5882.79
```

**整数幂()函数的运算**

pow()函数将“double”作为参数，并返回一个“double”值。这个函数并不总是适用于整数。一个这样例子是功率(5，2)。当分配给一个整数时，它在一些编译器上输出 24，在其他一些编译器上运行良好。但是功率(5，2)没有任何分配给整数输出 25。

*   这是因为 5 <sup>2</sup> (即 25)可能存储为 24.99999999 或 25.00000000001，因为返回类型是双精度的。当赋给 int 时，25.00000000001 变成 25，但 24.9999999 将给出输出 24。
*   为了克服这一点，并以整数格式输出准确的答案，我们可以将 0.5 添加到结果中，并将其类型转换为 **int** ，例如(int)(pow(5，2)+0.5)将给出正确的答案(在上面的示例中为 25)，而与编译器无关。

## C

```cpp
// C program to illustrate
// working with integers in
// power function
#include <math.h>
#include <stdio.h>

int main()
{
    int a;

    // Using typecasting for
    // integer result
    a = (int)(pow(5, 2) + 0.5);
    printf("%d", a);

    return 0;
}
```

## C++

```cpp
// CPP program to illustrate
// working with integers in
// power function
#include <bits/stdc++.h>
using namespace std;
int main()
{
    int a;

    // Using typecasting for
    // integer result
    a = (int)(pow(5, 2) + 0.5);
    cout << a;

    return 0;
}
```

**Output:** 

```cpp
25
```

本文由**阿鲁什·达米亚**和**贾丁·戈亚尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。