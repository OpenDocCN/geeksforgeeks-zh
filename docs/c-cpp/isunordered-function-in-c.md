# c++ 中的 isunordered()函数

> 原文:[https://www.geeksforgeeks.org/isunordered-function-in-c/](https://www.geeksforgeeks.org/isunordered-function-in-c/)

**is norded()**函数在 **< cmath.h >** 中定义，检查第一个参数的值是否可以与第二个参数进行有意义的比较。如果第一个参数不能与第二个参数进行有意义的比较(即一个或两个都是 NAN)，则返回 1，否则返回 0。

**语法:**

```cpp
bool isunordered(float x, float y);
```

**或**T0

**参数:**取**两个值 x 和 y** 即检查是否无序的值。

**返回:**如果 x 或 y 的值为 NAN，则返回 **1** ，否则返回 **0** 。

下面的程序说明了 C++ 中的 isunordered()函数:

**例 1:-**

```cpp
// c++ program to demonstrate
// example of isunordered() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
  float x=6.3;
  float y=sqrt(-9);

  cout<<"The value of x is= "<< x << endl;
  cout<<"The value of y is= "<< y << endl;

  //Now it return whether x or y are unordered values or not
  cout<<"isunordered(x, y) = "<<isunordered(x, y);
  return 0;
}
```

**输出:**

```cpp
The value of x is= 6.3
The value of y is= -nan
isunordered(x, y) = 1

```

**解释:**在示例 1 中，y 的值是 NAN，这就是函数返回 1 的原因。

**例 2:-**

```cpp
// c++ program to demonstrate
// example of isunordered() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
  float x=4.6;
  float y=9.2;

  cout<<"The value of x is= "<< x << endl;
  cout<<"The value of y is= "<< y << endl;

  //Now it return whether x or y are unordered values or not
  cout<<"isunordered(x, y) = "<<isunordered(x, y);
  return 0;
}
```

**输出:**

```cpp
The value of x is= 4.6
The value of y is= 9.2
isunordered(x, y) = 0

```

**解释:**在示例 2 中，x 和 y 的值不是 NAN，这就是函数返回 0 的原因。