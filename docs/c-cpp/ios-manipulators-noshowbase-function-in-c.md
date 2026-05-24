# ios 操纵器 noshowbase()函数在 C++ 中

> 原文:[https://www . geeksforgeeks . org/IOs-机械手-noshowbase-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-noshowbase-function-in-c/)

C++ 中**流操纵器**的 **noshowbase()** 方法用于清除指定字符串流的 showbase 格式标志。此标志仅显示十进制的 nitegers。

**语法:**

```cpp
ios_base& noshowbase (ios_base& str)

```

**参数:**该方法接受**字符串**作为参数，该参数是要清除格式标志的流。

**返回值:**该方法返回设置了 noshowbase 格式标志的**流**字符串。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of noshowbase() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the integer
    int num = 50;

    // Using noshowbase()
    cout << "noshowbase flag: "
         << oct
         << noshowbase
         << num << endl;

    return 0;
}
```

**输出:**

```cpp
noshowbase flag: 62

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of noshowbase() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the integer
    int num = 50;

    // Using noshowbase()
    cout << "noshowbase flag: "
         << hex
         << noshowbase
         << num << endl;

    return 0;
}
```

**输出:**

```cpp
noshowbase flag: 32

```

**参考:**T2】http://www.cplusplus.com/reference/ios/noshowbase/