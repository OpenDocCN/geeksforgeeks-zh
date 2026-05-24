# ios 操纵器大写()函数在 C++ 中

> 原文:[https://www . geeksforgeeks . org/IOs-机械手-大写-函数 in-c/](https://www.geeksforgeeks.org/ios-manipulators-uppercase-function-in-c/)

C++ 中**流操纵器**的**大写()**方法用于设置指定字符串流的大写格式标志。该标志使输出操作使用大写字母而不是小写字母。

**语法:**

```cpp
ios_base& uppercase (ios_base& str)

```

**参数:**该方法接受**字符串**作为参数，该参数是受格式标志影响的流。

**返回值:**该方法返回设置了大写格式标志的**流**字符串。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of uppercase() function

#include <iostream>
#include <sstream>

using namespace std;

int main()
{

    // Initializing the int
    int n = 20;

    // Using uppercase()
    cout << "uppercase flag: "
         << showbase << oct
         << uppercase
         << n << endl;

    return 0;
}
```

**输出:**

```cpp
uppercase flag: 024

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of uppercase() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the int
    int n = 20;

    // Using uppercase()
    cout << "uppercase flag: "
         << showbase << hex
         << uppercase
         << n << endl;

    return 0;
}
```

**输出:**

```cpp
uppercase flag: 0X14

```

**参考:**T2】http://www.cplusplus.com/reference/ios/uppercase/