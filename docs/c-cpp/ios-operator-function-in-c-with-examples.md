# ios 操作员！()函数在 C++ 中的使用示例

> 原文:[https://www . geesforgeks . org/IOs-operator-function-in-c-with-examples/](https://www.geeksforgeeks.org/ios-operator-function-in-c-with-examples/)

**符！()**方法中的 **ios 类**在 C++ 中被用来对此流的任何错误标志进行设置。这包括故障位或坏位。

**语法:**

```cpp
bool operator!()  const;

```

**参数:**此方法不接受任何参数。

**返回值:**如果该流设置了任何错误位，则该方法返回真，否则返回假。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of operator!() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Stream
    stringstream ss;

    // Using operator!() function
    if (!ss) {
        cout << "Error bit is set.\n";
    }
    else {
        cout << "No error bit is set.\n";
    }

    return 0;
}
```

**输出:**

```cpp
No error bit is set.

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of operator!() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Stream
    stringstream ss;
    ss.clear(ss.failbit);

    // Using operator!() function
    if (!ss) {
        cout << "Error bit is set.\n";
    }
    else {
        cout << "No error bit is set.\n";
    }

    return 0;
}
```

**输出:**

```cpp
Error bit is set.

```

**参考:**[hhttp://www.cplusplus.com/reference/ios/ios/operator！/](//www.cplusplus.com/reference/ios/ios/operator!/)