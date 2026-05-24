# c++ 中复数的 polar()函数

> 原文:[https://www . geesforgeks . org/polar-function-for-complex-number-in-CPP/](https://www.geeksforgeeks.org/polar-function-for-complex-number-in-cpp/)

复数的**极坐标()**功能在**复数**头文件中定义。极函数用于从相角和幅值中求复数。

**语法:**

```cpp
polar(mag, angle)

```

**参数:**

*   **mag:** 表示复数的大小。
*   **角度:**表示相角。

**返回:**这个函数返回一个复数，这个复数是由相位角和幅度得到的。

下面的程序说明了上述功能

**程序 1:**

```cpp
// C++ program to demonstrate
// example of polar() function.
#include <bits/stdc++.h>
using namespace std;

// driver function
int main ()
{
  cout << "The complex number whose magnitude is 4.0";
  cout << " and phase angle 1.5";

  // use of polar() function
  cout << " is " << polar (4.0, 1.5) << endl;

  return 0;
}
```

**Output:**

```cpp
The complex number whose magnitude is 4.0 and phase angle 1.5 is (0.282949,3.98998)

```

**程序 2:**

```cpp
// C++ program to demonstrate
// example of polar() function.
#include <bits/stdc++.h>
using namespace std;

// driver function
int main ()
{
  cout << "The complex number whose magnitude is 2.0";
  cout << " and phase angle 0.5";

  // use of polar() function
  cout << " is " << polar (2.0, 0.5) << endl;

  return 0;
}
```

**Output:**

```cpp
The complex number whose magnitude is 2.0 and phase angle 0.5 is (1.75517,0.958851)

```