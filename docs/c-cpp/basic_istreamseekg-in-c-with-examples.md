# c++ 中的 basic_istream::seekg()，示例

> 原文:[https://www . geesforgeks . org/basic _ is treaseekg-in-c-with-examples/](https://www.geeksforgeeks.org/basic_istreamseekg-in-c-with-examples/)

**basic_stream::seekg()** 方法用于设置要从输入流中提取的下一个字符的位置。该函数存在于 iostream 头文件中。下面是相同的语法:

**头文件:**

```cpp
#include<iostream>

```

**语法:**

```cpp
basic_istream& seekg (pos_type pos);

```

**参数:**

*   **pos** :表示缓冲区中的新位置。

**返回值:**该函数返回 basic_istream 对象。

下面是说明**STD::basic _ is tream::seekg()**的程序

**程序 1:**

```cpp
// C++ code for basic_istream::seekg()

#include <bits/stdc++.h>
using namespace std;

// Driver code
int main()
{
    string str = "Geeks for Geeks";
    istringstream gfg(str);
    string a, b;

    gfg >> a;
    gfg.seekg(0); // rewind
    gfg >> b;

    cout << "a = " << a << endl;
    cout << "b = " << b << endl;
}
```

**输出:**

```cpp
a = Geeks
b = Geeks

```

**程序二:**

```cpp
// C++ code for basic_istream::seekg()

#include <bits/stdc++.h>
using namespace std;

// Driver code
int main()
{
    string str = "Geeks for Geeks";
    istringstream gfg(str);
    string a, b;

    gfg >> a;
    gfg.seekg(6); // rewind
    gfg >> b;

    cout << "a = " << a << endl;
    cout << "b = " << b << endl;
}
```

**输出:**

```cpp
a = Geeks
b = for

```

**参考:**T2【http://www . cplusplus . com/Reference/is tream/basic _ is tream/seekg/