# ios eof()函数在 C++ 中的应用举例

> 原文:[https://www . geesforgeks . org/IOs-eof-function-in-c-with-examples/](https://www.geeksforgeeks.org/ios-eof-function-in-c-with-examples/)

C++ 中 **ios 类**的 **eof()** 方法用于检查流是否引发了任何 eof(文件结束)错误。这意味着该函数将检查该流是否设置了 eofbit。

**语法:**

```cpp
bool eof() const;

```

**参数:**此方法不接受任何参数。

**返回值:**如果流设置了 eofbit，则该方法返回 true，否则返回 false。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of eof() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Stream
    stringstream ss;

    // Using eof() function
    bool isEOF = ss.eof();

    // print result
    cout << "is stream eof: "
         << isEOF << endl;

    return 0;
}
```

**输出:**

```cpp
is stream eof: 0

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of eof() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Stream
    stringstream ss;
    ss.clear(ss.eofbit);

    // Using eof() function
    bool isEOF = ss.eof();

    // print result
    cout << "is stream eof: "
         << isEOF << endl;

    return 0;
}
```

**输出:**

```cpp
is stream eof: 1

```

**参考:**T2【hhttp://www . cplusplus . com/Reference/IOs/IOs/eof/