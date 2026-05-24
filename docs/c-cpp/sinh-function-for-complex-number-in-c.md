# c++ 中复数的 sinh()函数

> 原文:[https://www . geesforgeks . org/sinh-function-for-complex-number-in-c/](https://www.geeksforgeeks.org/sinh-function-for-complex-number-in-c/)

**sinh()** 函数是在*复杂的*头文件中定义的 C++ 内置函数。该功能是 *cmath* 头文件中可用的 **sinh()** 功能的复杂版本。此函数用于计算复数 z 的复双曲正弦值。
**语法:**

```cpp
template<class T> complex<T> 
       sinh (const complex<T>& z );
```

**参数:**

*   **z:** 该方法取一个代表复数的强制参数 **z** 。

**返回值:**此函数返回复数 z 的双曲正弦值。
下面的程序说明了 C++ 中 complex 头文件的 sinh()函数:
**例 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// example of sinh() function.

#include <bits/stdc++.h>
using namespace std;

int main ()
{
  complex<double> complexnumber (0.0, 1.0);

  // use of sinh() function for complex number
  cout << "The sinh of " << complexnumber << " is "
                     << sinh(complexnumber) <<endl;

  return 0;
}
```

**Output:** 

```cpp
The sinh of (0,1) is (0,0.841471)
```

**例 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate
// example of sinh() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
  complex<double> complexnumber (1.0, 0.0);

  // use of sinh() function for complex number
  cout << "The sinh of " << complexnumber << " is "
                     << sinh(complexnumber) << endl;

  return 0;
}
```

**Output:** 

```cpp
The sinh of (1,0) is (1.1752,0)
```