# c++ 中 ratio_less_equal()函数

> 原文:[https://www . geesforgeks . org/ratio _ less _ equal-function-in-c/](https://www.geeksforgeeks.org/ratio_less_equal-function-in-c/)

**比率小于等于()**是 C++ 中的一个内置函数，它检查比率 R1 是否小于或等于比率 R2。如果比率小于或等于比率 2，则返回真，否则返回假。
**语法:**

```cpp
template < class ratio1_name, class ratio2_name > ratio_less_equal
```

**模板参数**该功能接受两个要比较的模板参数*比率 1* 和*比率 2* 。
**返回值:**如果比率 1 小于或等于比率 2，则该函数返回布尔值 true，否则返回 false。
以下程序说明了上述功能:
**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// ratio_less_equal function
// when both the ratios are equal
#include <iostream>
#include <ratio>
using namespace std;
int main()
{
    typedef ratio<3, 9> ratio1;
    typedef ratio<1, 3> ratio2;

    // check if R1<=R2
    if (ratio_less_equal<ratio1, ratio2>::value)
        cout << "3/9 is less than or equal to 1/3";
    else
        cout << "3/9 is greater than 1/3";

    return 0;
}
```

**Output:** 

```cpp
3/9 is less than or equal to 1/3
```

**程序 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// ratio_less_equal function
// to show less than
#include <iostream>
#include <ratio>
using namespace std;
int main()
{
    typedef ratio<1, 3> ratio1;
    typedef ratio<1, 2> ratio2;

    // check if R1<=R2
    if (ratio_less_equal<ratio1, ratio2>::value)
        cout << "1/3 is less than or equal to 1/2";
    else
        cout << "1/3 is greater than 1/2";

    return 0;
}
```

**Output:** 

```cpp
1/3 is less than or equal to 1/2
```

**程序 3:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// ratio_less_equal function
// to show when greater than
#include <iostream>
#include <ratio>
using namespace std;
int main()
{
    typedef ratio<1, 8> ratio1;
    typedef ratio<1, 10> ratio2;

    // check if R1<=R2
    if (ratio_less_equal<ratio1, ratio2>::value)
        cout << "1/8 is less than or equal to 1/10";
    else
        cout << "1/8 is greater than 1/10";

    return 0;
}
```

**Output:** 

```cpp
1/8 is greater than 1/10
```