# 标准::basic_istream::getline 用 C++ 举例

> 原文:[https://www . geeksforgeeks . org/stdbasic _ is treamgetline-in-c-with-examples/](https://www.geeksforgeeks.org/stdbasic_istreamgetline-in-c-with-examples/)

**STD::basic _ istream::getline**用于从流中提取字符，直到行尾，或者提取的字符是定界字符。定界字符是新的行字符，即 **'\n'** 。如果使用文件进行输入，当到达文件末尾时，此功能也将停止提取字符。

**头文件:**

```cpp
#include <iostream>

```

**语法:**

```cpp
basic_istream& getline (char_type* a, 
                            streamsize n )

basic_istream& getline (char_type* a, 
                            streamsize n, 
                             char_type delim);

```

**参数:**接受以下参数:

*   **N:** 表示 a 所指向字符的最大数量
*   **a:** 是存储字符的字符串指针。
*   **流:**是一个明确的定界符。

**返回值:**返回 **basic_istream** 对象。

下面是演示 **basic_istream::getline()** 的程序:

**程序 1:**

```cpp
// C++ program to demonstrate
// basic_istream::getline

#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Given string
    istringstream gfg("123|aef|5h");

    // Array to store the above string
    // after streaming
    vector<array<char, 4> > v;

    // Use function getline() to stream
    // the given string with delimeter '|'
    for (array<char, 4> a;
         gfg.getline(&a[0], 4, '|');) {
        v.push_back(a);
    }

    // Print the strings after streaming
    for (auto& it : v) {
        cout << &it[0] << endl;
    }

    return 0;
}
```

**输出:**

```cpp
123
aef
5h

```

**程序二:**

```cpp
// C++ program to demonstrate
// basic_istream::getline

#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Given string
    istringstream gfg("GeeksforGeeks, "
                      " A, Computer, Science, "
                      "Portal, For, Geeks");

    // Array to store the above string
    // after streaming
    vector<array<char, 40> > v;

    // Use function getline() to stream
    // the given string with delimeter ', '
    for (array<char, 40> a;
         gfg.getline(&a[0], 40, ', ');) {
        v.push_back(a);
    }

    // Print the strings after streaming
    for (auto& it : v) {
        cout << &it[0] << endl;
    }

    return 0;
}
```

**输出:**

```cpp
GeeksforGeeks
A
Computer
Science
Portal
For
Geeks

```

**参考:**T2【http://www . cplusplus . com/Reference/is tream/basic _ is tream/getline/