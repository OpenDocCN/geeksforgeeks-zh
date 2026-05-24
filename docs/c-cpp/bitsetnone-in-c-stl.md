# c++ STL 中的 bit set none()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/bitsetnone-in-c-STL/

**位集::none()** 是 C++ 中的内置 STL，如果其位都没有设置，则返回 True。如果设置了最少一位，则返回假。

**语法:**

```cpp
bool none() 

```

**参数:**函数不接受参数。

**返回值:**函数返回一个布尔值。如果没有设置布尔值**为真**。如果至少设置了一位，则为**假**。

下面的程序说明了 bitset::none()函数。

**程序 1:**

## C++

```cpp
// C++ program to illustrate the
// bitset::none() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialization of bitset
    bitset<4> b1(string("1100"));
    bitset<6> b2(string("000000"));

    // Function to check if none of
    // the bits are set or not in b1
    bool result1 = b1.none();
    if (result1)
        cout << b1 << " has no bits set"
             << endl;
    else
        cout << b1 << " has a minimum of one bit set"
             << endl;

    // Function to check if none of
    // the bits are set or not in b1
    bool result2 = b2.none();
    if (result2)
        cout << b2 << " has no bits set"
             << endl;
    else
        cout << b2 << " has a minimum of one bit set"
             << endl;

    return 0;
}
```

**Output:** 

```cpp
1100 has a minimum of one bit set
000000 has no bits set

```

**程序 2:**

## C++

```cpp
// C++ program to illustrate the
// bitset::none() function
// when the input is a number
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialization of bitset
    bitset<3> b1(4);
    bitset<6> b2(0);

    // Function to check if none of
    // the bits are set or not in b1
    bool result1 = b1.none();
    if (result1)
        cout << b1 << " has no bits set"
             << endl;
    else
        cout << b1 << " has a minimum of one bit set"
             << endl;

    // Function to check if none of
    // the bits are set or not in b1
    bool result2 = b2.none();
    if (result2)
        cout << b2 << " has no bits set"
             << endl;
    else
        cout << b2 << " has a minimum of one bit set"
             << endl;

    return 0;
}
```

**Output:** 

```cpp
100 has a minimum of one bit set
000000 has no bits set

```