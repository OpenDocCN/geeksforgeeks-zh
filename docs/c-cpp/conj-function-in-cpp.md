# c++ 中的 conj()函数，示例

> 原文:[https://www.geeksforgeeks.org/conj-function-in-cpp/](https://www.geeksforgeeks.org/conj-function-in-cpp/)

**conj()** 函数在**复杂的**头文件中定义。这个函数用来求复数 z 的共轭，如果我们把复数 z 表示为(实数，img)，那么它的共轭就是(实数，-img)。
**语法:**

```cpp
template<class T> complex<T> 
     conj (const complex<T>& Z);
```

**参数:**

*   **z:** 该方法取一个代表复数的强制参数 **z** 。

**返回值:**该函数返回复数 z 的**共轭**。
下面的程序说明了 C++ 中复数的 conj()函数:
**例 1:-**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// example of conj() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main ()
{
  complex<double> complexnumber (3.0, 2.4);

  cout << "The conjugate of " << complexnumber << " is: ";

  // use of conj() function
  cout << conj(complexnumber) << endl;
  return 0;
}
```

**Output:** 

```cpp
The conjugate of (3,2.4) is: (3,-2.4)
```

**实施例 2:-**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// example of conj() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main ()
{
  complex<double> complexnumber (2.0, 9.0);

  cout << "The conjugate of " << complexnumber << " is: ";

  // use of conj() function
  cout << conj(complexnumber) << endl;
  return 0;
}
```

**Output:** 

```cpp
The conjugate of (2,9) is: (2,-9)
```