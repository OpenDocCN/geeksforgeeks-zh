# c++ STL 中的位集运算符[]

> 原文:[https://www.geeksforgeeks.org/bitset-operator-in-c-stl/](https://www.geeksforgeeks.org/bitset-operator-in-c-stl/)

**位集::运算符[]** 是 C++ STL 中的内置函数，用于为位集的任何索引赋值。

**语法:**

```cpp
bitset_operator[index] = value

```

**参数:**参数**索引**指定要赋值的**位置**。

**返回值:**函数将值返回到索引处的位。

下面的程序说明了 bitset::operator[]函数。

**程序 1:**

## C++

```cpp
// C++ program to illustrate the
// bitset::operator[]
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initialization of bitset
    // by zeros of size 6
    bitset<6> b;

    // initialises second index as 1
    b[2] = 1;

    // initialises fifth index as 1
    b[5] = 1;

    // prints the bitset
    cout << "The bitset after assigning values is: " << b;
    return 0;
}
```

**Output:** 

```cpp
The bitset after assigning values is: 100100

```

**程序 2:**

## C++

```cpp
// C++ program to illustrate the
// bitset::operator[]
// assign value from a index
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initialization of bitset
    // by zeros of size 6
    bitset<6> b;

    // initialises second index as 1
    b[2] = 1;

    // initialises fifth index as the same as b[2]
    b[3] = b[2];

    b[0] = b[5];

    // prints the bitset
    cout << "The bitset after assigning values is: " << b;
    return 0;
}
```

**Output:** 

```cpp
The bitset after assigning values is: 001100

```

**程序 3:**

## C++

```cpp
// C++ program to illustrate the
// bitset::operator[]
// prints the value of bit at index
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initialization of bitset
    // by zeros of size 6
    bitset<6> b;

    // initialises second index as 1
    b[2] = 1;

    // initialises fifth index as the same as b[2]
    b[3] = b[2];

    b[0] = b[5];

    cout << "The bit value at index 3 is " << b[3];
    return 0;
}
```

**Output:** 

```cpp
The bit value at index 3 is 1

```