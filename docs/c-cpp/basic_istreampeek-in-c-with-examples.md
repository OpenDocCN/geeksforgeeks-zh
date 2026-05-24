# c++ 中的 basic_istream::peek()，示例

> 原文:[https://www . geeksforgeeks . org/basic _ is treampeek-in-c-with-examples/](https://www.geeksforgeeks.org/basic_istreampeek-in-c-with-examples/)

**STD::basic _ is tream::peek()**用于从输入流中读取下一个字符，而不提取它。这个函数不接受任何参数，只返回输入字符串中的下一个字符。下面是相同的语法:

**头文件:**

```cpp
#include<iostream>

```

**语法:**

```cpp
int peek();

```

**返回值:****STD::basic _ is tream::peek()**返回输入字符串中的下一个字符。

以下是以更好的方式理解**STD::basic _ is tream::peek()**实现的程序:

**程序 1:**

```cpp
// C++ code for std::basic_istream::peek()
#include <bits/stdc++.h>
using namespace std;

// main method
int main()
{
    istringstream gfg("GeeksforGeeks");

    char c1 = gfg.peek();
    char c2 = gfg.get();
    char c3 = gfg.get();

    cout << "The first character is: "
         << c1 << endl
         << " and the next is: "
         << c3 << endl;
}
```

**输出:**

```cpp
The first character is: G 
and the next is: e

```

**程序二:**

```cpp
// C++ code for std::basic_istream::peek()
#include <bits/stdc++.h>
using namespace std;

// main method
int main()
{
    istringstream gfg("Computer");

    char c1 = gfg.peek();
    char c2 = gfg.get();
    char c3 = gfg.get();

    cout << "The first character is: "
         << c1 << endl
         << " and the next is: "
         << c3 << endl;
}
```

**输出:**

```cpp
The first character is: C 
and the next is: o

```

**程序 3:**

```cpp
// C++ code for std::basic_istream::peek()
#include <bits/stdc++.h>
using namespace std;

// main method
int main()
{
    istringstream gfg("Laptop");

    char c1 = gfg.peek();
    char c2 = gfg.get();
    char c3 = gfg.get();
    char c4 = gfg.get();

    cout << "The first character is: "
         << c1 << endl
         << " and the next is: "
         << c3 << endl
         << " after that next is: "
         << c4 << endl;
}
```

**输出:**

```cpp
The first character is: L 
and the next is: a 
after that next is: p

```

**参考:**T2【http://www . cplusplus . com/Reference/is tream/basic _ is tream/peek/