# c++ 中 ratio_less()函数

> 原文:[https://www.geeksforgeeks.org/ratio_less-function-in-c/](https://www.geeksforgeeks.org/ratio_less-function-in-c/)

**比率 _less()** 是 C++ 中的一个内置函数，它检查比率 R1 是否小于比率 R2。如果比率小于比率 2，则返回真，否则返回假。

**语法:**

```cpp
template < class ratio1_name, class ratio2_name > ratio_less

```

**模板参数:**该功能接受两个要比较的模板参数*比率 1* 和*比率 2* 。

**返回值:**函数返回一个布尔值，如果比率 1 小于比率 2，则该值为真，否则返回假。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// ratio_less function
#include <iostream>
#include <ratio>
using namespace std;
int main()
{
    typedef ratio<3, 9> ratio1;
    typedef ratio<1, 3> ratio2;

    // check if R1<R2
    if (ratio_less<ratio1, ratio2>::value)
        cout << "3/9 is less than 1/3";
    else
        cout << "3/9 is not less than 1/3";

    return 0;
}
```

**Output:**

```cpp
3/9 is not less than 1/3

```

**程序 2:**

```cpp
// C++ program to illustrate the
// ratio_less function
#include <iostream>
#include <ratio>
using namespace std;
int main()
{
    typedef ratio<1, 2> ratio1;
    typedef ratio<4, 7> ratio2;

    // check if R1<R2
    if (ratio_less<ratio1, ratio2>::value)
        cout << "1/2 is less than 4/7";
    else
        cout << "1/2 is not less than 4/7";

    return 0;
}
```

**Output:**

```cpp
1/2 is less than 4/7

```