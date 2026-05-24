# c++ STL 中的位集::flip()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/bitsetflip-in-c-STL/

**位集::flip()** 是 C++ 中的内置 STL，用于翻转位。如果函数中没有传递参数，那么它会翻转所有的位值，将 0 转换为 1，将 1 转换为 0。如果传递了参数位置，它只会翻转该位置的位。

**语法:**

```cpp
bitset_name.flip(int pos)

```

**参数:**该功能接受一个参数**位置**，该参数不是强制的。如果参数位置被传递，它只翻转索引位置的位(索引位置是从右边开始计算的)。如果没有传递参数，它会翻转所有的位值，将 0 转换为 1，将 1 转换为 0。

**返回值:**该函数根据传入或未传入的参数翻转所有位值，并返回数字的新二进制表示。

下面的程序说明了 bitset::flip()函数。

**程序 1:**

```cpp
// CPP program to illustrate the
// bitset::flip() function
// when no parameter is passed
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initialization of bitset
    bitset<4> b1(string("1100"));
    bitset<6> b2(string("010010"));

    // Printing the bitset after flipping the bits
    cout << b1 << " after applying flip() function returns ";
    cout << b1.flip() << endl;

    cout << b2 << " after applying flip() function returns ";
    cout << b2.flip();

    return 0;
}
```

**Output:**

```cpp
0011 after applying flip() function returns 1100
101101 after applying flip() function returns 010010

```

**程序 2:**

```cpp
// CPP program to illustrate the
// bitset::flip() function
// when parameter is passed

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Initialization of bitset
    bitset<4> b1(string("1100"));
    bitset<7> b2(string("0100100"));

    // Printing the bitset after flipping the bits
    cout << b1 << " after applying flip(3) function returns ";
    cout << b1.flip(3) << endl;

    cout << b2 << " after applying flip(6) function returns ";
    cout << b2.flip(6);

    return 0;
}
```

**Output:**

```cpp
0100 after applying flip(3) function returns 1100
1100100 after applying flip(6) function returns 0100100

```