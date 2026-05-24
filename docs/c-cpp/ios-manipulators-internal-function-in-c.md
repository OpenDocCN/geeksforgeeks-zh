# ios 操纵器内部()函数在 C++ 中

> 原文:[https://www . geeksforgeeks . org/IOs-机械手-内部-函数-in-c/](https://www.geeksforgeeks.org/ios-manipulators-internal-function-in-c/)

C++ 中**流操纵器**的**内部()**方法用于为指定的字符串流设置 adjustfield 格式标志。该标志将 adjustfield 设置为内部。这意味着输出中的数字将通过在指定的内部点插入填充字符来填充到字段宽度。

**语法:**

```cpp
ios_base& internal (ios_base& str)

```

**参数:**该方法接受**字符串**作为参数，该参数是受格式标志影响的流。

**返回值:**该方法返回设置了内部格式标志的**流**字符串。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of internal() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the integer
    double x = -1.23;

    cout.precision(5);

    // Using internal()
    cout << "internal flag: ";

    cout.width(12);
    cout << internal << x << endl;

    return 0;
}
```

**输出:**

```cpp
internal flag: -       1.23

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of internal() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the integer
    double x = -1.23;

    cout.precision(5);

    // Using internal()
    cout << "internal flag: ";

    cout.width(12);
    cout << internal << x << endl;

    return 0;
}
```

**输出:**

```cpp
internal flag: -       1.23

```

**参考:**T2】http://www.cplusplus.com/reference/ios/internal/