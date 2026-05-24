# c++ 中的 basic_istream::putback()，示例

> 原文:[https://www . geeksforgeeks . org/basic _ is treamputback-in-c-with-examples/](https://www.geeksforgeeks.org/basic_istreamputback-in-c-with-examples/)

**basic_istream::putback()** 用于将字符放回输入字符串中。该功能存在于 **iostream** 头文件中。下面是相同的语法:

**头文件:**

```cpp
#include<iostream>

```

**语法:**

```cpp
basic_istream& putback (char_type ch);

```

**参数:**

*   **ch:** 表示要放回输入字符串的字符。

**返回值:****iostream::basic_istream::putback()**返回 basic _ istream 对象。

以下是以更好的方式理解**STD::basic _ istream::putback()**实现的程序:

**程序 1:**

```cpp
// C++ code for basic_istream::putback()
#include <bits/stdc++.h>

using namespace std;

int main()
{
    stringstream gfg1("GeeksforGeeks");
    gfg1.get();

    // putback A into the input string
    if (gfg1.putback('A'))
        cout << gfg1.rdbuf() << endl;

    istringstream gfg2("GeeksforGeeks");
    gfg2.get();

    if (gfg2.putback('A'))
        cout << gfg2.rdbuf() << endl;
    else
        cout << "putback is failed here\n";

    gfg2.clear();

    // Again putback G in the string
    if (gfg2.putback('G'))
        cout << gfg2.rdbuf() << endl;
}
```

**输出:**

```cpp
AeeksforGeeks
putback is failed here
GeeksforGeeks

```

**程序二:**

```cpp
// C++ code for basic_istream::putback()
#include <bits/stdc++.h>

using namespace std;

int main()
{
    stringstream gfg1("GOOD");
    gfg1.get();

    // putback B into the input string
    if (gfg1.putback('B'))
        cout << gfg1.rdbuf() << endl;

    istringstream gfg2("GOOD");
    gfg2.get();

    if (gfg2.putback('B'))
        cout << gfg2.rdbuf() << endl;
    else
        cout << "putback is failed here\n";

    gfg2.clear();

    // Again putback G in the string
    if (gfg2.putback('G'))
        cout << gfg2.rdbuf() << endl;
}
```

**输出:**

```cpp
BOOD
putback is failed here
GOOD

```

**参考:**T2】http://www.cplusplus.com/reference/istream/istream/putback/