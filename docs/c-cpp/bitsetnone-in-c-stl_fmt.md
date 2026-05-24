# C++ STL 中的 `bitset::none()`

> 哎哎哎:# t0]https://www . geeksforgeeks . org/bitsetnone-in-c-STL/

`bitset::none()` 是 C++ 中的内置 STL 函数，如果其位集中的所有位都没有被设置，则返回 `true`。如果至少设置了一位，则返回 `false`。

## 语法

```cpp
bool none()
```

## 参数

函数不接受参数。

## 返回值

函数返回一个布尔值。如果没有设置任何位，返回值为 `true`。如果至少设置了一位，则返回值为 `false`。

下面的程序说明了 `bitset::none()` 函数。

## 程序 1

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

## 程序 2

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