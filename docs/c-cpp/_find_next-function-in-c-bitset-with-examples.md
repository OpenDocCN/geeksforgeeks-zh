# _Find_next()函数在 C++ 位集中用示例

> 原文:[https://www . geesforgeks . org/_ find _ next-function-in-c-bit set-with-examples/](https://www.geeksforgeeks.org/_find_next-function-in-c-bitset-with-examples/)

**_Find_next()** 是 [C++ Biteset 类](https://www.geeksforgeeks.org/c-bitset-and-its-application/)中的内置函数，返回一个整数，该整数表示索引后位集中下一个设置位的位置。如果索引后没有设置位，_Find_next(索引)将返回位集的大小。

**语法:**

```cpp

iterator bitset._Find_next(index)
           or
int bitset._Find_next(index)

```

**参数:**该函数接受一个强制参数**索引**，该索引指定在位集中找到第一个设置位后的索引。

**返回值:**该函数返回一个整数，该整数是指指定索引后位集中下一个设置位的位置。如果索引(指定的索引)后没有设置位，_Find_next(索引)将返回位集的大小。

以下是上述功能的图示:

**例:**

```cpp
// C++ program for illustration
// of _Find_next() function

#include <bits/stdc++.h>
using namespace std;

#define M 32

int main()
{
    // default constructor initializes with all bits 0
    bitset<M> bset;
    bitset<M> bset1;
    bitset<M> bset2;

    // 00000000000000000000000000100000
    bset[5] = 1;

    // 00000000000000000000010000100000
    bset[10] = 1;

    // 01000000000000100001000000000001
    bset1[0] = bset1[12] = bset1[17] = bset1[30] = 1;

    // function returns the next set bit
    // in bitset after index 0
    cout << "Next set bit after index 0 in bset\n";
    cout << bset._Find_next(0) << "\n";

    // function returns the next set bit
    // in bitset after index 6
    cout << "Next set bit after index 6 in bset\n";
    cout << bset._Find_next(6) << "\n";

    // finds all set bits in bitset bset1
    cout << "Find all set bits in bset1\n";
    for (int i = bset1._Find_first();
         i < bset1.size();
         i = bset1._Find_next(i))
        cout << i << " ";
    cout << "\n";

    // function returns bset2.size()
    // when there isn't any set bit after index
    cout << "Next set bit after index 5 in bset2\n";
    cout << bset2._Find_next(5) << "\n";

    return 0;
}
```

**输出:**

```cpp
Next set bit after index 0 in bset
5
Next set bit after index 6 in bset
10
Find all set bits in bset1
0 12 17 30 
Next set bit after index 5 in bset2
32

```

**参考:**[https://gcc . GNU . org/online docs/libstdc++/libstdc++-html-USERS-3.4/bitset-source . html](https://gcc.gnu.org/onlinedocs/libstdc++/libstdc++-html-USERS-3.4/bitset-source.html)