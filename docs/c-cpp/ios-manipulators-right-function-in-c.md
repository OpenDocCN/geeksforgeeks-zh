# ios 操纵器右()函数在 C++ 中

> 原文:[https://www . geesforgeks . org/IOs-机械手-右-函数 in-c/](https://www.geeksforgeeks.org/ios-manipulators-right-function-in-c/)

C++ 中**流操纵器**的 **right()** 方法用于为指定的字符串流设置 adjustfield 格式标志。该标志将 adjustfield 设置为右侧。这意味着输出中的数字将通过在开头插入填充字符填充到字段宽度。

**语法:**

```cpp
ios_base& right (ios_base& str)

```

**参数:**该方法接受**字符串**作为参数，该参数是受格式标志影响的流。

**返回值:**该方法返回设置了内部格式标志的**流**字符串。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of right() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the integer
    double x = -1.23;

    cout.precision(5);

    // Using right()
    cout << "right flag: ";

    cout.width(12);
    cout << right << x << endl;

    return 0;
}
```

**输出:**

```cpp
right flag:        -1.23

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of right() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the integer
    double x = -1.23;

    cout.precision(5);

    // Using right()
    cout << "right flag: ";

    cout.width(12);
    cout << right << x << endl;

    return 0;
}
```

**输出:**

```cpp
right flag:        -1.23

```

**参考:**T2】http://www.cplusplus.com/reference/ios/right/