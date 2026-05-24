# ios 操纵器 scientific()函数在 C++ 中

> 原文:[https://www . geeksforgeeks . org/IOs-机械手-scientific-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-scientific-function-in-c/)

C++ 中**流操纵器**的 **scientific()** 方法用于设置指定字符串流的 floatfield 格式标志。此标志将浮动字段设置为科学。这意味着，浮点值将被写入科学符号。

**语法:**

```cpp
ios_base& scientific (ios_base& str)

```

**参数:**该方法接受**字符串**作为参数，该参数是受格式标志影响的流。

**返回值:**该方法返回设置了内部格式标志的**流**字符串。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of scientific() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the float values
    double x = 1.23;

    cout.precision(5);

    cout << "without scientific flag: "
         << x << endl;

    // Using scientific()
    cout << "with scientific flag: "
         << scientific << x << endl;

    return 0;
}
```

**输出:**

```cpp
without scientific flag: 1.23
with scientific flag: 1.23000e+00

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of scientific() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the float values
    double x = 1.0;

    cout.precision(5);

    cout << "without scientific flag: "
         << x << endl;

    // Using scientific()
    cout << "with scientific flag: "
         << scientific << x << endl;

    return 0;
}
```

**输出:**

```cpp
without scientific flag: 1
with scientific flag: 1.00000e+00

```

**例 3:**

```cpp
// C++ code to demonstrate
// the working of scientific() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the float values
    double x = 1.23e9;

    cout.precision(5);

    cout << "without scientific flag: "
         << x << endl;

    // Using scientific()
    cout << "with scientific flag: "
         << scientific << x << endl;

    return 0;
}
```

**输出:**

```cpp
without scientific flag: 1.23e+09
with scientific flag: 1.23000e+09

```

**参考:**T2】http://www.cplusplus.com/reference/ios/scientific/