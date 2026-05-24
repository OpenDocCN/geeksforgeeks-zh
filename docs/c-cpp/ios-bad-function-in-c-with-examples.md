# ios 坏()函数在 C++ 中用示例

> 原文:[https://www . geesforgeks . org/IOs-bad-function-in-c-with-examples/](https://www.geeksforgeeks.org/ios-bad-function-in-c-with-examples/)

C++ 中 **ios 类**的 **bad()** 方法用于检查流是否引发了任何错误。这意味着这个函数将检查这个流是否设置了坏位。

**语法:**

```cpp
bool bad() const;

```

**参数:**此方法不接受任何参数。

**返回值:**如果流设置了坏位，这个方法返回真，否则返回假。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of bad() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Stream
    stringstream ss;

    // Using bad() function
    bool isBad = ss.bad();

    // print result
    cout << "is stream bad: "
         << isBad << endl;

    return 0;
}
```

**输出:**

```cpp
is stream bad: 0

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of bad() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Stream
    stringstream ss;
    ss.clear(ss.badbit);

    // Using bad() function
    bool isBad = ss.bad();

    // print result
    cout << "is stream bad: "
         << isBad << endl;

    return 0;
}
```

**输出:**

```cpp
is stream bad: 1

```

**参考:**T2【hhttp://www . cplusplus . com/Reference/IOs/IOs/bad/