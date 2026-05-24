# c++ 中的 round()

> 原文:[https://www.geeksforgeeks.org/round-in-cpp/](https://www.geeksforgeeks.org/round-in-cpp/)

**舍入**用于舍入给定的数字，该数字可以是浮点数或双数。它返回与在**舍入**函数中提供的参数最接近的整数值，中间的情况从零舍入。代替 round()， **std::round()** 也可以使用。
使用的头文件->**cmath****ctg math**

**语法:**

```cpp
Parameters: x, value to be rounded
double round (double x);
float round (float x);
long double round (long double x);
double round (T x);           
// additional overloads for integral types

Returns: The value of x rounded to the nearest 
integral (as a floating-point value).

```

```cpp
// C++ code to demonstrate the
// use of round() function
#include <cmath>
#include <iostream>
using namespace std;

// Driver program
int main()
{
    // initializing value
    double x = 12.5, y = 13.3, z = 14.8;

    // Displaying the nearest values
    // of x, y and z
    cout << "Nearest value of x :" << round(x) << "\n";
    cout << "Nearest value of y :" << round(y) << "\n";
    cout << "Nearest value of z :" << round(z) << "\n";

    // For lround
    cout << "lround(-0.0) = " << lround(-0.0) << "\n";
    cout << "lround(2.3) = " << lround(2.3) << "\n";
    cout << "lround(2.5) = " << lround(2.5) << "\n";
    cout << "lround(2.7) = " << lround(2.7) << "\n";
    cout << "lround(-2.3) = " << lround(-2.3) << "\n";
    cout << "lround(-2.5) = " << lround(-2.5) << "\n";
    cout << "lround(-2.7) = " << lround(-2.7) << "\n";

    // For llround
    cout << "llround(-0.01234) = " << llround(-0.01234) << "\n";
    cout << "llround(2.3563) = " << llround(2.3563) << "\n";
    cout << "llround(2.555) = " << llround(2.555) << "\n";
    cout << "llround(2.7896) = " << llround(2.7896) << "\n";
    cout << "llround(-2.323) = " << llround(-2.323) << "\n";
    cout << "llround(-2.5258) = " << llround(-2.5258) << "\n";
    cout << "llround(-2.71236) = " << llround(-2.71236) << "\n";

    return 0;
}
```

输出:

```cpp
Nearest value of x :13
Nearest value of y :13
Nearest value of z :15
lround(-0.0) = 0
lround(2.3) = 2
lround(2.5) = 3
lround(2.7) = 3
lround(-2.3) = -2
lround(-2.5) = -3
lround(-2.7) = -3
llround(-0.01234) = 0
llround(2.3563) = 2
llround(2.555) = 3
llround(2.7896) = 3
llround(-2.323) = -2
llround(-2.5258) = -3
llround(-2.71236) = -3

```

这里，在上面的程序中，我们刚刚计算了给定浮点或双精度值的最近整数值。
已经计算准确。

**可能的应用**

1.  **处理分数和小数的不匹配:**舍入数字的一种用法是在将 1/3 转换为小数时，将小数点右边的三个都缩短。大多数情况下，当我们需要处理十进制中的 1/3 时，我们会使用四舍五入的数字 0.33 或 0.333。当小数中没有精确的等份时，我们通常只使用小数点右边的两三位数字。
2.  **Changing multiplied result :** There will be difference between multiplication of 25, 75 and 0.25, 0.75 we get 0.875 .We started with 2 digits to the right of the decimal point and ended up with 4\. Many times we will just round up the result to 0.19 .

    ```cpp
    // C+++ code for above explanation
    #include <cmath>
    #include <iostream>
    using namespace std;

    // Driver program
    int main()
    {
        // Initializing values for int type
        long int a1 = 25, b1 = 30;

        // Initializing values for double type
        double a2 = .25, b2 = .30;
        long int ans_1 = (a1 * b1);
        double ans_2 = (a2 * b2);

        // Rounded result for both
        cout << "From first multiplication :" << round(ans_1) << "\n";
        cout << "From second multiplication :" << round(ans_2) << "\n";
        return 0;
    }
    ```

    输出:

    ```cpp
        From first multiplication :750
        From second multiplication :0

    ```

3.  **快速计算:**假设需要快速计算，我们取近似值，然后计算最近的答案。例如，经过任何计算，我们得到的答案是 298.78，通过四舍五入，我们得到的绝对答案是 300。
4.  **获取估计值:**有时候想取整数而不是小数。通常你感兴趣的是四舍五入到最接近的 10，100，1000 或百万的倍数。例如，2006 年，人口普查部门确定纽约市人口为 8，214，426 人。这个数字很难记住，如果我们说纽约市的人口是 800 万，这是一个很好的估计，因为确切的数字并没有什么真正的区别。

**参考**:www.cplusplus.com www.mathworksheetcenter.com

本文由**喜马拉雅冉冉**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。