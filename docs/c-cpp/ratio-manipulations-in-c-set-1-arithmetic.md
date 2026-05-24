# c++ 中的比率操作|集合 1(算术)

> 原文:[https://www . geeksforgeeks . org/ratio-manuals-in-c-set-1-算术/](https://www.geeksforgeeks.org/ratio-manipulations-in-c-set-1-arithmetic/)

本文在
[下面讨论了一种添加比率的方法。添加两个分数的程序](https://www.geeksforgeeks.org/program-to-add-two-fractions/)
上述方法涉及一项繁琐而冗长的任务。但是 C++ 有一个头文件，它允许我们使用各种内置的模板别名来操作比率。这个头文件是在 C++ 11 以后引入的。
**1。ratio_add** :-该模板别名用于**添加两个 ratio**，以最简单的形式返回**结果。它返回两个成员常量， **num** 和 **den** 表示分子和分母。
**2。ratio _ 减法** :-该模板别名用于**减去两个 ratio**，以最简单的形式**返回**结果。它返回两个成员常量， **num** 和 **den** 表示分子和分母。它**从比率 1** 中减去比率 2。** 

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate the working of
// ratio_add and ratio_subtract
#include<iostream>
#include<ratio> // for ratio manipulation
using namespace std;
int main()
{
    // Declaring ratios
    typedef ratio<5, 4> ratio1;
    typedef ratio<3, 4> ratio2;

    // Summing two ratios
    typedef ratio_add< ratio1, ratio2 > sum;

    // Subtracting two ratios
     typedef ratio_subtract< ratio1, ratio2 > diff;

    // printing sum of ratios
    cout << "The sum of ratios is : ";
    cout << sum::num << "/" << sum::den;
    cout << endl;

    // printing difference of ratios
    cout << "The difference of ratios is : ";
    cout << diff::num << "/" << diff::den;
    cout << endl;

    return 0;

}
```

输出:

```cpp
The sum of ratios is : 2/1
The difference of ratios is : 1/2
```

**3。ratio _ 乘** :-该模板别名用于**乘两个 ratio**，以最简单的形式返回**结果。它返回两个成员常量， **num** 和 **den** 表示分子和分母。
**4。ratio_divide** :-该模板别名用于**对两个比率**进行划分，并以最简单的形式**返回**结果。它返回两个成员常量， **num** 和 **den** 表示分子和分母。它**将比率 1 除以比率 2** 。** 

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate the working of
// ratio_multiply and ratio_divide
#include<iostream>
#include<ratio> // for ratio manipulation
using namespace std;
int main()
{
    // Declaring ratios
    typedef ratio<5, 4> ratio1;
    typedef ratio<3, 4> ratio2;

    // Multiplying two ratios
    typedef ratio_multiply< ratio1, ratio2 > prod;

    // Dividing two ratios
     typedef ratio_divide< ratio1, ratio2 > div;

    // printing product of ratios
    cout << "The product of ratios is : ";
    cout << prod::num << "/" << prod::den;
    cout << endl;

    // printing division of ratios
    cout << "The division of ratios is : ";
    cout << div::num << "/" << div::den;
    cout << endl;

    return 0;

}
```

输出:

```cpp
The product of ratios is : 15/16
The division of ratios is : 5/3
```

本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。