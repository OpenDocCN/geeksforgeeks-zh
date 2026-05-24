# c++ 中的 basic_istream::unget()，示例

> 原文:[https://www . geeksforgeeks . org/basic _ is treamunget-in-c-with-examples/](https://www.geeksforgeeks.org/basic_istreamunget-in-c-with-examples/)

**basic_istream::unget()** 用于取消字符的锁定，用于将位置减少一个字符，并使提取的字符可供再次使用。
T3】头文件:T5】

```cpp
<iostream>

```

**语法:**

```cpp
basic_istream& unget();

```

**参数:****basic _ is tream::unget()**方法不接受任何参数。
**返回值:**函数 **basic_istream::unget()** 返回 basic_istream 对象。
下面是程序说明**STD::basic _ istream::unget():**
**程序 1:**

## CPP14

```cpp
// C++ code for basic_istream::unget()
#include <bits/stdc++.h>
using namespace std;

// Driver code
int main()
{
    // Declare string stream
    istringstream gfg("GeeksforGeeks");

    char a = gfg.get();
    if (gfg.unget()) {
        char b = gfg.get();
        cout << "We got: " << a << endl;
        cout << "After ungetting the "
             << "character once again"
             << " we got: "
             << b << endl;
    }

    return 0;
}
```

**Output:**

```cpp
We got: G
After ungetting the character once again we got: G

```