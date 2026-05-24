# c++ 中的 NaN 是什么，怎么查？

> 原文:[https://www . geesforgeks . org/nan-in-CPP-it 是什么以及如何检查它/](https://www.geeksforgeeks.org/nan-in-cpp-what-is-it-and-how-to-check-for-it/)

**什么是 NaN？**
NaN，缩写为“Not a Number”，是一个例外，通常出现在表达式导致数字无法表示的情况下。例如负数的平方根。

```cpp
// C++ code to demonstrate NaN exception
#include<iostream>
#include<cmath> // for sqrt()
using namespace std;
int main()
{
    float a = 2, b = -2;

    // Prints the number (1.41421)
    cout << sqrt(a) << endl;

    // Prints "nan" exception
    // sqrt(-2) is complex number
    cout << sqrt(b) << endl;

    return 0;
}
```

输出:

```cpp
1.41421
-nan

```

**如何检查 NaN？**

**方法 1:使用[比较(==)运算符](https://www.geeksforgeeks.org/operators-in-c-set-2-relational-and-logical-operators/)。**
在这种方法中，我们通过比较一个数字和它本身来检查它是否复杂。如果结果为真，则该数字为**而非**复数即实数。但如果结果为假，则返回“nan”，即数字为复数。

```cpp
// C++ code to check for NaN exception
// using "==" operator
#include<iostream>
#include<cmath> // for sqrt()
using namespace std;
int main()
{
    float a = sqrt(2);
    float b = sqrt(-2);

    // Returns true, a is real number
    // prints "Its a real number"
    a==a? cout << "Its a real number" << endl:
          cout << "Its NaN" << endl;

    // Returns false, b is complex number
    // prints "Its nan"
    b==b? cout << "Its a real number" << endl:
          cout << "Its NaN" << endl;

    return 0;

}
```

输出:

```cpp
Its a real number
Its NaN

```

 **方法二:使用内置函数“isnan()”。**
检查 NaN 的另一种方法是使用“isnan()”函数，如果一个数字是复数，该函数返回 true，否则返回 false。

```cpp
// C++ code to check for NaN exception
// using "isnan()" 
#include<iostream>
#include<cmath> // for sqrt() and isnan()
using namespace std;
int main()
{
    float a = sqrt(2);
    float b = sqrt(-2);

    // Returns false as a 
    // is real number
    isnan(a)? cout << "Its NaN" << endl:
              cout << "Its a real number" << endl;

    // Returns true as b is  NaN
    isnan(b)? cout << "Its NaN" << endl:
              cout << "Its a real number" << endl;

    return 0;    
}
```

输出:

```cpp
Its a real number
Its NaN

```

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。