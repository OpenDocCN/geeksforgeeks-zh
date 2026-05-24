# c++ STL 中的 bitset all()函数

> 原文:[https://www.geeksforgeeks.org/bitsetall-in-c-stl/](https://www.geeksforgeeks.org/bitsetall-in-c-stl/)

**位集::all()** 是 C++ STL 中的一个内置函数，如果所有位都设置为数字的二进制表示，并且在位集中进行了初始化，则返回 True。如果未设置所有位，则返回假。

**语法:**

```cpp
bool bitset_name.all() 

```

**参数:**该函数不接受任何参数。

**返回值:**函数返回一个布尔值。如果所有的位都被设置，返回的布尔值为真，否则返回的值为假，

下面的程序说明了 bitset::all()函数。

**程序 1:**

```cpp
// CPP program to illustrate the
// bitset::all() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initialization of bitset
    bitset<4> b1(string("1100"));
    bitset<6> b2(string("111111"));

    // Function that checks if all
    // the bits are set or not
    bool result1 = b1.all();
    if (result1)
        cout << b1 << " has all bits set"
             << endl;
    else
        cout << b1 << " does not have all bits set"
             << endl;

    // Function that checks if all
    // the bits are set or not
    bool result2 = b2.all();
    if (result2)
        cout << b2 << " has all bits set"
             << endl;
    else
        cout << b2 << " does not have all bits set"
             << endl;

    return 0;
}
```

**Output:**

```cpp
1100 does not have all bits set
111111 has all bits set

```

**程序 2:**

```cpp
// CPP program to illustrate the
// bitset::all() function
// when the input is as a number

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initialization of bitset
    bitset<2> b1(3);
    bitset<3> b2(5);

    // Function that checks if all
    // the bits are set or not
    bool result1 = b1.all();
    if (result1)
        cout << b1 << " has all bits set"
             << endl;
    else
        cout << b1 << " does not have all bits set"
             << endl;

    // Function that checks if all
    // the bits are set or not
    bool result2 = b2.all();
    if (result2)
        cout << b2 << " has all bits set"
             << endl;
    else
        cout << b2 << " does not have all bits set"
             << endl;

    return 0;
}
```

**Output:**

```cpp
11 has all bits set
101 does not have all bits set

```