# C++ 中复数的 tanh()函数

> 原文: [https://www.geeksforgeeks.org/tanh-function-for-complex-number-in-c/](https://www.geeksforgeeks.org/tanh-function-for-complex-number-in-c/)

复数的 `tanh()` 函数在 `complex` 头文件中定义。这个函数是 `cmath` 头文件的 `tanh()` 函数的复杂版本。此函数用于计算复数 `z` 的复双曲正切。

**语法:**

```cpp
template<class T> complex<T> tanh (const complex<T>& z );
```

**参数:**

*   `z`: 该方法取一个代表复数的强制参数 `z`。

**返回值:**
此函数返回复数 `z` 的双曲正切值。

下面的程序说明了 C++ 中的 `tanh()` 函数:

### 示例 1:

```cpp
// C++ program to demonstrate
// example of tanh() function.

#include <bits/stdc++.h>
using namespace std;

int main ()
{
  complex<double> complexnumber (0.0, 1.0);

// use of tanh() function for complex number
  cout << "The tanh of " << complexnumber << " is "
                     << tanh(complexnumber) <<endl;

return 0;
}
```

**Output:**

```cpp
The tanh of (0,1) is (0,1.55741)
```

### 示例 2:

```cpp
// C++ program to demonstrate
// example of tanh() function.

#include <bits/stdc++.h>
using namespace std;

int main ()
{
  complex<double> complexnumber (1.0, 0.0);

// use of tanh() function for complex number
  cout << "The tanh of " << complexnumber << " is "
                     << tanh(complexnumber) << endl;

return 0;
}
```

**Output:**

```cpp
The tanh of (1,0) is (0.761594,0)
```