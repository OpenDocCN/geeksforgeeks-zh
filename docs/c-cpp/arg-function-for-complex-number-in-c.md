# c++ 中复数的 arg()函数

> 原文:[https://www . geesforgeks . org/arg-function-for-complex-number-in-c/](https://www.geeksforgeeks.org/arg-function-for-complex-number-in-c/)

复数的 **arg()** 函数在**复数**头文件中定义。这个函数用来返回复数 z 的参数。

**语法:**

```cpp
template<class T> T arg (const complex<T>& z);

```

**参数:**

*   **z:** 表示给定的复数。

**Return:** 返回复数的自变量。

以下程序说明了上述功能

**例 1:**

```cpp
// C++ program to demonstrate
// example of arg() function.

#include <bits/stdc++.h>
using namespace std;

int main ()
{
  // defines the complex number: (5.0 + 12.0i)
  complex<double> complexnumber (5.0, 12.0);

  // prints the argument of the complex number
  cout << "The argument of " << complexnumber << " is: ";
  cout << arg(complexnumber) << endl;

  return 0;
}
```

**Output:**

```cpp
The argument of (5,12) is: 1.17601

```

**例 2:**

```cpp
// C++ program to demonstrate
// example of arg() function

#include <bits/stdc++.h>
using namespace std;

int main ()
{
  // defines the complex number: (4.0+3.0i)
  complex<double> complexnumber (4.0, 3.0);

  // prints the argument of the complex number
  cout << "The argument of " << complexnumber << " is: ";
  cout << arg(complexnumber) << endl;

  return 0;
}
```

**Output:**

```cpp
The argument of (4,3) is: 0.643501

```