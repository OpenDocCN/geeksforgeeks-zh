# c++ 中的范数()函数，示例

> 原文:[https://www . geesforgeks . org/norm-function-in-CPP-with-examples/](https://www.geeksforgeeks.org/norm-function-in-cpp-with-examples/)

**定额()**功能在**复杂**头文件中定义。这个函数用来返回复数 z 的平方值。

**语法:**

```cpp
template<class T> T norm (const complex<T>& z);

```

**参数:**

*   **z:** 表示给定的复数。

**返回:**返回复数的平方大小。

以下程序说明了上述功能

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of norm() function.

#include <bits/stdc++.h>
using namespace std;

// driver function
int main ()
{
  // initializing the complex: (5.0+12.0i)
  complex<double> complexnumber (5.0, 12.0);

  // use of norm()function
  cout << "The norm of " << complexnumber << " is ";
  cout << norm(complexnumber) << endl;

  return 0;
}
```

**Output:**

```cpp
The norm of (5,12) is 169

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of norm() function.

 #include <bits/stdc++.h>
using namespace std;

// driver function
int main ()
{
  // initializing the complex: (4.0+3.0i)
  complex<double> complexnumber (4.0, 3.0);

  // use of norm()function
  cout << "The norm of " << complexnumber << " is ";
  cout << norm(complexnumber) << endl;

  return 0;
}
```

**Output:**

```cpp
The norm of (4,3) is 25

```