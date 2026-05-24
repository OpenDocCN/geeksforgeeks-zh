# 在 C++ STL 中设置任意()位

> 原文:[https://www.geeksforgeeks.org/bitset-any-in-c-stl/](https://www.geeksforgeeks.org/bitset-any-in-c-stl/)

**位集::any()** 是 C++ STL 中的一个内置函数，如果一个数字中至少设置了一个位，它就会返回 True。如果没有设置所有的位，或者如果数字为零，则返回假。

**语法:**

```cpp
bool any() 

```

**参数:**函数不接受任何参数。

**返回值:**函数返回一个布尔值。这样返回的布尔值是**真**，如果它的任何一位被设置。如果没有设置位，则为**假**。

下面的程序说明了 bitset::any()函数。

**程序 1:**

## C++

```cpp
// C++ program to illustrate the
// bitset::any() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialization
    bitset<4> b1(string("1100"));
    bitset<6> b2(string("000000"));

    // function to check if any of
    // its bits are set or not
    bool result1 = b1.any();
    if (result1)
        cout << b1 << " has a minimum of one-bit set"
             << endl;
    else
        cout << b1 << " does not have any bits set"
             << endl;

    // function to check if any of
    // its bits are set or not
    bool result2 = b2.any();
    if (result2)
        cout << b2 << "  has a minimum of one-bit set"
             << endl;
    else
        cout << b2 << " does not have any bits set"
             << endl;

    return 0;
}
```

**Output:** 

```cpp
1100 has a minimum of one-bit set
000000 does not have any bits set

```

**程序 2:**

## C++

```cpp
// C++ program to illustrate the
// bitset::any() function
// when the input is as a number

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialization
    bitset<2> b1(3);
    bitset<3> b2(0);

    // function to check if any of
    // its bits are set or not
    bool result1 = b1.any();
    if (result1)
        cout << b1 << " has a minimum of one-bit set"
             << endl;
    else
        cout << b1 << " does not have any bit set"
             << endl;

    // function to check if any of
    // its bits are set or not
    bool result2 = b2.any();
    if (result2)
        cout << b2 << " has a minimum of one-bit set"
             << endl;
    else
        cout << b2 << " does not have any bit set"
             << endl;

    return 0;
}
```

**Output:** 

```cpp
11 has a minimum of one-bit set
000 does not have any bit set

```