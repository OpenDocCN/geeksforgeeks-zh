# c++ STL 中的位集计数()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/bitsetcount-in-c-STL/

**bitset::count()** 是 C++ 中的一个内置 STL，它返回一个数的二进制表示中的集合位数。

**语法:**

```cpp
int count() 

```

**参数:**函数不接受参数。

**返回值:**函数返回设置的位数。如果传递的数字是整数，它将返回 1 的总数或数字的二进制表示中的设置位数。

下面的程序说明了 bitset::count()函数。

**程序 1:**

```cpp
// CPP program to illustrate the
// bitset::count() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initialisation of a bitset
    bitset<4> b1(string("1100"));
    bitset<6> b2(string("001000"));

    // Function to count the
    // number of set bits in b1
    int result1 = b1.count();
    cout << b1 << " has " << result1
         << " set bit\n";

    // Function to count the
    // number of set bits in b2
    int result2 = b2.count();
    cout << b2 << " has " << result2
         << " set bit";

    return 0;
}
```

**Output:**

```cpp
1100 has 2 set bit
001000 has 1 set bit

```

**程序 2:**

```cpp
// CPP program to illustrate the
// bitset::count() function
// when the input is an integer
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initialisation of a bitset
    bitset<4> b1(16);
    bitset<4> b2(18);

    // Function to count the
    // number of set bits in b1
    int result1 = b1.count();
    cout << b1 << " has " << result1
         << " set bit\n";

    // Function to count the
    // number of set bits in b2
    int result2 = b2.count();
    cout << b2 << " has " << result2
         << " set bit";

    return 0;
}
```

**Output:**

```cpp
0000 has 0 set bit
0010 has 1 set bit

```