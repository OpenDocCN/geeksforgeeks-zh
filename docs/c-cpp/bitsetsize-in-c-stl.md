# c++ STL 中的位集大小()

> 原文:[https://www.geeksforgeeks.org/bitsetsize-in-c-stl/](https://www.geeksforgeeks.org/bitsetsize-in-c-stl/)

**bitset::size()** 是 C++ 中的内置 STL，返回总位数。

**语法:**

```cpp
bitset_name.size()
```

**参数:**函数不接受参数。

**返回值:**函数返回一个表示位数的整数值。它最终返回初始化位集时给定的大小。

下面的程序说明了 bitset::size()函数。

**程序 1:**

## C++

```cpp
// C++ program to illustrate the
// bitset::size() function
// when input is a string

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialization of the bitset string
    bitset<4> b1(string("1100"));
    bitset<6> b2(string("010010"));

    // prints the size i.e.,
    // the number of bits in "1100"
    cout << "The number of bits in " << b1
         << " is " << b1.size() << endl;

    // prints the size i.e.,
    // the number of bits in  "010010"
    cout << "The number of bits in " << b2
         << " is " << b2.size() << endl;

    return 0;
}
```

**Output:** 

```cpp
The number of bits in 1100 is 4
The number of bits in 010010 is 6
```

**程序 2:**

## C++

```cpp
// C++ program to illustrate the
// bitset::size() function
// when input is a number

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialization of the bitset string
    bitset<3> b1(5);
    bitset<5> b2(17);

    // prints the size i.e.,
    // the number of bits in 5
    cout << "The number of bits in " << b1
         << " is " << b1.size() << endl;

    // prints the size i.e.,
    // the number of bits in 17
    cout << "The number of bits in "
         << b2 << " is " << b2.size() << endl;

    return 0;
}
```

**Output:** 

```cpp
The number of bits in 101 is 3
The number of bits in 10001 is 5
```