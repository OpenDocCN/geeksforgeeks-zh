# ios good()函数在 C++ 中用示例

> 原文:[https://www . geeksforgeeks . org/IOs-good-function-in-c-with-examples/](https://www.geeksforgeeks.org/ios-good-function-in-c-with-examples/)

C++ 中 **ios 类**的 **good()** 方法用来检查流是否足够好可以工作。这意味着该函数将检查该流是否引发了任何错误。

**语法:**

```cpp
bool good() const;

```

**参数:**此方法不接受任何参数。

**返回值:**如果流是好的，这个方法返回真，否则返回假。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of good() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Stream
    stringstream ss;

    // Using good() function
    bool isGood = ss.good();

    // print result
    cout << "is stream good: "
         << isGood << endl;

    return 0;
}
```

**输出:**

```cpp
is stream good: 1

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of good() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Stream
    stringstream ss;
    ss.clear(ss.eofbit);

    // Using good() function
    bool isGood = ss.good();

    // print result
    cout << "is stream good: "
         << isGood << endl;

    return 0;
}
```

**输出:**

```cpp
is stream good: 0

```

**参考:**T2【hhttp://www . cplusplus . com/Reference/IOs/IOs/good/