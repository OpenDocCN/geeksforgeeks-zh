# STD::numeric _ limits<t>::denorm _ min()用 C++ 举例</t>

> 原文:[https://www . geesforgeks . org/stdnumeric _ limitstdnorm _ min-in-c-with-example/](https://www.geeksforgeeks.org/stdnumeric_limitstdenorm_min-in-c-with-example/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 中的**STD::numeric _ limits<T>::denorm _ min()**函数存在于< limits >头文件中。该函数用于寻找最小的非零反规格化值。

**头文件:**

```cpp
#include<limits>

```

**模板类:**

```cpp
static T denorm_min() throw();
static constexpr T denorm_min() noexcept;

```

**语法:**

```cpp
std::numeric_limits<T>::denorm_min()

```

**参数:**函数**STD::numeric _ limits<T>:denorm _ min()**不接受任何参数。

**返回值:**函数**STD::numeric _ limits<T>:denorm _ min()**返回数据类型 **T** 的最小非零反规格化值。

下面是用 C++ 演示**标准:数值极限<T>:denorm _ min()**的程序:

**程序:**

```cpp
// C++ program to illustrate
// std::numeric_limits<T>::denorm_min()
#include <bits/stdc++.h>
#include <limits>
using namespace std;

// Driver Code
int main()
{

    // Print the denormalised value for
    // different data types
    cout << "For float: "
         << numeric_limits<float>::denorm_min()
         << endl;

    cout << "For int: "
         << numeric_limits<int>::denorm_min()
         << endl;

    cout << "For double: "
         << numeric_limits<double>::denorm_min()
         << endl;

    cout << "For long int: "
         << numeric_limits<long int>::denorm_min()
         << endl;

    cout << "For long double: "
         << numeric_limits<long double>::denorm_min()
         << endl;
    return 0;
}
```

**Output:**

```cpp
For float: 1.4013e-45
For int: 0
For double: 4.94066e-324
For long int: 0
For long double: 3.6452e-4951

```

**参考:**[https://en . cppreference . com/w/CPP/type/numeric _ limits/denorm _ min](https://en.cppreference.com/w/cpp/types/numeric_limits/denorm_min)