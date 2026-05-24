# c++ STL 中的 bitset set()函数

> 原文:[https://www.geeksforgeeks.org/bitset-set-function-in-c-stl/](https://www.geeksforgeeks.org/bitset-set-function-in-c-stl/)

**位集::set()** 是 C++ 中的内置 STL，它将位设置为特定索引处的给定值。如果没有传递参数，它会将所有位设置为 1。如果只传递了一个参数，它会将该特定索引处的位设置为 1。

**语法:**

```cpp
set(int index, bool val) 

```

**参数:**该函数接受两个参数，描述如下:

1.  **Index–** This parameter specifies the position where the bit must be set. This parameter is optional.
2.  **val–**该参数指定一个布尔值，该值必须在索引处设置。该参数是可选的。

    如果没有参数通过，则将所有位设置为 1。如果只传递了一个参数，它将设置该索引处的位。

**返回值:**函数不返回任何内容。

下面的程序说明了 bitset::set()函数。

**程序 1:**

```cpp
// CPP program to illustrate the
// bitset::set() function
// when parameter is not passed

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initialization of bitset
    bitset<4> b1(string("1100"));
    bitset<6> b2(string("100100"));

    // Function that resets all bits
    cout << "Before applying set() function: "
         << b1 << endl;

    b1.set();
    cout << "After applying set() function: "
         << b1 << endl;

    // Function that resets all bits
    cout << "Before applying set() function: "
         << b2 << endl;

    b2.set();
    cout << "After applying set() function: "
         << b2 << endl;

    return 0;
}
```

**输出:**

```cpp
Before applying set() function: 1100
After applying set() function: 1111
Before applying set() function: 100100
After applying set() function: 111111

```

**程序二:**

```cpp
// CPP program to illustrate the
// bitset::set() function
// when parameter is passed

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initialization of bitset
    bitset<4> b1(string("1100"));
    bitset<6> b2(string("100100"));

    // Function that resets all bits
    cout << "Before applying set() function: "
         << b1 << endl;

    // single parameter is passed
    b1.set(1);
    cout << "After applying set(1) function: "
         << b1 << endl;

    // Function that resets all bits
    cout << "Before applying set() function: "
         << b2 << endl;

    // both parameters is passed
    b2.set(2, 0);
    b2.set(4, 1);
    cout << "After applying set(2, 0) and"
         << " set(4, 1) function: " << b2 << endl;

    return 0;
}
```

**输出:**

```cpp
Before applying set() function: 1100
After applying set(1) function: 1110
Before applying set() function: 100100
After applying set(2, 0) and set(4, 1) function: 110000

```