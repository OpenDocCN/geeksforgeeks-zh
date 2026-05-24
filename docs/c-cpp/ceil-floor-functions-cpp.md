# c++ 中的天花板和地板功能

> 原文:[https://www.geeksforgeeks.org/ceil-floor-functions-cpp/](https://www.geeksforgeeks.org/ceil-floor-functions-cpp/)

在数学和计算机科学中，下限和上限函数分别将一个实数映射到最大的前一个或最小的后一个整数。

**floor(x) :** 返回小于或等于 x 的最大整数(即:向下舍入最近的整数)。

```cpp
// Here x is the floating point value.
// Returns the largest integer smaller 
// than or equal to x 
double floor(double x)  
```

楼层示例:

```cpp
Input : 2.5
Output : 2

Input : -2.1
Output : -3

Input : 2.9
Output : 2

```

```cpp
// C++ program to demonstrate floor function
#include <iostream>
#include <cmath>
using namespace std;

// Driver function
int main()
{
    // using floor function which return
    // floor of input value
    cout << "Floor is : " << floor(2.3) << endl;
    cout << "Floor is : " << floor(-2.3) << endl;

    return 0;
}
```

输出:

```cpp
Floor is : 2
Floor is : -3

```

**ceil(x) :** 返回大于或等于 x 的最小整数(即:四舍五入最近的整数)。

```cpp
// Here x is the floating point value.
// Returns the smallest integer greater 
// than or equal to x 
double ceiling(double x)  
```

天花板的例子:

```cpp
Input : 2.5
Output : 3

Input : -2.1
Output : -2

Input : 2.9
Output : 3

```

```cpp
// C++ program to demonstrate ceil function
#include <iostream>
#include <cmath>
using namespace std;

// Driver function
int main()
{
    // using ceil function which return
    // floor of input value
    cout << " Ceil is : " << ceil(2.3) << endl;
    cout << " Ceil is : " << ceil(-2.3) << endl;

    return 0;
}
```

```cpp
Ceil is : 3
Ceil is : -2

```

本文由**萨赫勒拉杰普特**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。