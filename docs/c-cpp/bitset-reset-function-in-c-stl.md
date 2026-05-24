# c++ STL 中的 bitset reset()函数

> 原文:[https://www . geesforgeks . org/bitset-reset-function-in-c-STL/](https://www.geeksforgeeks.org/bitset-reset-function-in-c-stl/)

**bitset::reset()** 是 C++ STL 中的内置函数，用于重置参数中给定索引处的位。如果没有参数被传递，那么所有的位被重置为零。

**语法:**

```cpp
reset(int index) 

```

**参数:**该函数接受一个参数*索引*，表示该位必须被重置为零的位置。如果未传递任何参数，位集中的所有位都会重置为零。

**返回值:**函数不返回任何内容。

下面的程序说明了 bitset::reset()函数。

**程序 1:**

```cpp
// CPP program to illustrate the
// bitset::reset() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initialization of bitset
    bitset<4> b1(string("1100"));
    bitset<6> b2(string("111111"));

    // Function that resets all bits
    cout << "Before applying reset() function: "
         << b1 << endl;

    b1.reset();
    cout << "After applying reset() function: "
         << b1 << endl;

    // Function that resets all bits
    cout << "Before applying reset() function: "
         << b2 << endl;

    b2.reset();
    cout << "After applying reset() function: "
         << b2 << endl;

    return 0;
}
```

**Output:**

```cpp
Before applying reset() function: 1100
After applying reset() function: 0000
Before applying reset() function: 111111
After applying reset() function: 000000

```

**程序 2:**

```cpp
// CPP program to illustrate the
// bitset::reset() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initialization of bitset
    bitset<4> b1(string("1101"));
    bitset<6> b2(string("111111"));

    // Function that resets all bits
    cout << "Before applying reset() function: "
         << b1 << endl;
    b1.reset(2);
    cout << "After applying reset(2) function: "
         << b1 << endl;

    // Function that resets all bits
    cout << "Before applying reset() function: "
         << b2 << endl;

    b2.reset(3);
    b2.reset(5);
    cout << "After applying reset(3) and reset(5) function: "
         << b2 << endl;

    return 0;
}
```

**Output:**

```cpp
Before applying reset() function: 1101
After applying reset(2) function: 1001
Before applying reset() function: 111111
After applying reset(3) and reset(5) function: 010111

```