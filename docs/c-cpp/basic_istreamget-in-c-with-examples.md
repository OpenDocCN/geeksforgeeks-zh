# c++ 中 basic_istream::get()示例

> 原文:[https://www . geeksforgeeks . org/basic _ is tream get-in-c-with-examples/](https://www.geeksforgeeks.org/basic_istreamget-in-c-with-examples/)

**basic_istream::get()** 用于获取角色。这个函数返回一个字符，否则它将返回文件的结尾。

**头文件:**

```cpp
<iostream>

```

**语法:**

```cpp
int_type get();

```

**参数:**方法 **basic_istream::get()** 不接受任何参数。

**返回值:**方法 **basic_istream::get()** 返回一个字符(如果可用)，否则返回文件结尾。

下面是说明 **basic_istream::get()** 的程序

**程序 1:**

```cpp
// C++ code for basic_istream::get()
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    // Declare string stream
    istringstream gfg("GeeksforGeeks");

    // Here we get H
    char a = gfg.get();
    cout << "First character is: "
         << a << endl;

    char b;
    // Here we got e
    gfg.get(b);
    cout << "After reading:" << a
         << " We got " << b << endl;

    return 0;
}
```

**输出:**

```cpp
First character is: G
After reading:G We got e

```

**程序二:**

```cpp
// C++ code for basic_istream::get()
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    // Declare string stream
    istringstream gfg("Computer");

    // Here we get C
    char a = gfg.get();
    cout << "First character is: "
         << a << endl;

    char b;
    // Here we got o
    gfg.get(b);
    cout << "After reading:" << a
         << " We got " << b << endl;

    char c;
    // Here we got m
    gfg.get(c);
    cout << "Now we got : "
         << c << endl;

    return 0;
}
```

**输出:**

```cpp
First character is: C
After reading:C We got o
Now we got : m

```

**参考:**[STD::basic _ is tream::get](http://www.cplusplus.com/reference/istream/basic_istream/get/)