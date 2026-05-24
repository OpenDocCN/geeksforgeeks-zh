# ios 在 C++ 中失败()函数，示例

> 原文:[https://www . geesforgeks . org/IOs-fail-function-in-c-with-examples/](https://www.geeksforgeeks.org/ios-fail-function-in-c-with-examples/)

C++ 中 **ios 类**的 **fail()** 方法用于检查流是否引发了任何失败错误。这意味着该函数将检查该流是否设置了 failbit。

**语法:**

```cpp
bool fail() const;

```

**参数:**此方法不接受任何参数。

**返回值:**如果流设置了故障位，该方法返回真，否则返回假。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of fail() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Stream
    stringstream ss;

    // Using fail() function
    bool isFail = ss.fail();

    // print result
    cout << "is stream fail: "
         << isFail << endl;

    return 0;
}
```

**输出:**

```cpp
is stream fail: 0

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of fail() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Stream
    stringstream ss;
    ss.clear(ss.failbit);

    // Using fail() function
    bool isFail = ss.fail();

    // print result
    cout << "is stream fail: "
         << isFail << endl;

    return 0;
}
```

**输出:**

```cpp
is stream fail: 1

```

**参考:**T2【hhttp://www . cplusplus . com/Reference/IOs/IOs/fail/