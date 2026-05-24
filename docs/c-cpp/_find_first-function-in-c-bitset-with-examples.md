# _Find_first()函数在 C++ 位集中用示例

> 原文:[https://www . geesforgeks . org/_ find _ first-function-in-c-bit set-with-examples/](https://www.geeksforgeeks.org/_find_first-function-in-c-bitset-with-examples/)

**_Find_first()** 是 [C++ Biteset 类](https://www.geeksforgeeks.org/c-bitset-and-its-application/)中的内置函数，返回一个整数，该整数表示位集中第一个设置位的位置。如果没有设置位，_Find_first()将返回位集的大小。

**语法:**

```cpp
iterator bitset._Find_first()
           or
int bitset._Find_first()

```

**参数:**函数不接受参数。

**返回值:**该函数返回一个**整数**，该整数指的是位组中**第一个设置位的位置。如果没有设置位，_Find_first()将返回位组**的**大小。**

下图是上述功能的图解:

```cpp
// C++ program for illustration
// of _Find_first() function

#include <bits/stdc++.h>
using namespace std;

#define M 32

int main()
{
    // default constructor initializes with all bits 0
    bitset<M> bset;
    bitset<M> bset1;

    // 00000000000000000000000000100000
    bset[5] = 1;

    // 00000000000000000000010000100000
    bset[10] = 1;

    // function returns the first set bit in Bitset
    cout << "position of first set bit in bset\n";
    cout << bset._Find_first() << "\n";

    // function returns bset1.size()
    // when no bit is set in bitset.
    cout << "position of first set bit in bset1\n";
    cout << bset1._Find_first() << "\n";

    return 0;
}
```

**输出:**

```cpp
position of first set bit in bset
5
position of first set bit in bset1
32

```

**参考:**[https://gcc . GNU . org/online docs/libstdc++/libstdc++-html-USERS-3.4/bitset-source . html](https://gcc.gnu.org/onlinedocs/libstdc++/libstdc++-html-USERS-3.4/bitset-source.html)