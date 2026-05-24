# c++ 中的比率操作|集合 2(比较)

> 原文:[https://www . geeksforgeeks . org/ratio-manuals-in-c-set-2-comparison/](https://www.geeksforgeeks.org/ratio-manipulations-in-c-set-2-comparison/)

操纵比率算法已经在下面的集合 1
[中讨论过了，在 C++ 中的比率操纵|集合 1(算术)](https://www.geeksforgeeks.org/ratio-manipulations-in-c-set-1-arithmetic/)
在本文中讨论了比率的比较。
**1。ratio_equal** :-该模板别名检查其参数**中的**比率**是否相等**。如果相等，则返回 true，否则返回 false。它返回一个**布尔成员**常量**“值”**。
**2。ratio_not_equal** :-该模板别名检查其参数中的**比率**是否为**不相等**。如果不相等则返回真，否则如果相等则返回假。它返回一个**布尔成员**常量**“值”**。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate the working of
// ratio_equal and ratio_not_equal
#include<iostream>
#include<ratio> // for ratio manipulation
using namespace std;
int main()
{
    // Declaring ratios 
    typedef ratio<10, 100> ratio1;
    typedef ratio<1, 10> ratio2;

    // Checking if ratios are equal using ratio_equal
    ratio_equal<ratio1, ratio2>::value ? 
              cout << "Ratios are equal" :
              cout << "Ratios are not equal";
    cout << endl;

     // Checking if ratios are not equal using ratio_not_equal
    ratio_not_equal<ratio1, ratio2>::value ? 
               cout << "Ratios are not equal" :
               cout << "Ratios are equal";

    return 0;

}
```

输出:

```cpp
Ratios are equal
Ratios are equal
```

**3。比率 _ 大于** :-该临时别名检查**比率 1 是否大于比率 2** 。它**返回一个布尔成员**常量**“值”**，如果比率 1 大于比率 2 则返回真，否则返回假。
**4。ratio_less** :-此临时别名检查**比率 1 是否小于比率 2** 。它**返回一个布尔成员**常量**“值”**，如果比率 1 小于比率 2 则返回真，否则返回假。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate the working of
// ratio_greater and ratio_less
#include<iostream>
#include<ratio> // for ratio manipulation
using namespace std;
int main()
{
    // Declaring ratios 
    typedef ratio<10, 100> ratio1;
    typedef ratio<11, 100> ratio2;

    // Checking if ratio1 is greater than ratio2 
    // using ratio_greater
    ratio_greater<ratio1, ratio2>::value ? 
             cout << "ratio1 is greater than ratio2" :
             cout << "ratio1 is not greater than ratio2";
    cout << endl;

    // Checking if ratio1 is less than ratio2 
    // using ratio_less
    ratio_less<ratio1, ratio2>::value ? 
             cout << "ratio1 is less than ratio2" :
             cout << "ratio1 is not less than ratio2";
    cout << endl;

    return 0;

}
```

输出:

```cpp
ratio1 is not greater than ratio2
ratio1 is less than ratio2
```

**5。比率大于等于** :-该临时别名检查**比率 1 是否大于或等于比率 2** 。它**返回一个布尔成员**常量**“值”**，如果比率 1 大于或等于比率 2 则返回真，否则返回假。
**6。ratio_less_equal** :-此临时别名检查**比率 1 是否小于或等于比率 2** 。它**返回一个布尔成员**常量**“值”**，如果比率 1 小于或等于比率 2 则返回真，否则返回假。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate the working of
// ratio_greater_equal and ratio_less_equal
#include<iostream>
#include<ratio> // for ratio manipulation
using namespace std;
int main()
{
    // Declaring ratios 
    typedef ratio<10, 100> ratio1;
    typedef ratio<1, 10> ratio2;

    // Checking if ratio1 is greater or equal than ratio2 
    // using ratio_greater_equal
    ratio_greater_equal<ratio1, ratio2>::value ? 
           cout << "ratio1 is greater or equal than ratio2" :
           cout << "ratio1 is not greater or equal than ratio2";
    cout << endl;

    // Checking if ratio1 is less or equal than ratio2 
    // using ratio_less_equal 
    ratio_less_equal<ratio1, ratio2>::value ? 
           cout << "ratio1 is less or equal than ratio2" :
           cout << "ratio1 is not less or equal than ratio2";
    cout << endl;

    return 0;

}
```

输出:

```cpp
ratio1 is greater or equal than ratio2
ratio1 is less or equal than ratio2
```

本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。