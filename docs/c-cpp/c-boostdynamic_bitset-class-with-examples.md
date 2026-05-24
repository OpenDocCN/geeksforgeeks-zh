# C++ boost::dynamic_bitset 类示例

> 原文:[https://www . geeksforgeeks . org/c-bootsdynamic _ bit set-class-with-examples/](https://www.geeksforgeeks.org/c-boostdynamic_bitset-class-with-examples/)

[**boost**](https://www.geeksforgeeks.org/advanced-c-boost-library/) 中有 150 多个库，其中一些最常用的库已经包含在 C++ 标准库中。**动态位集**是一个用于位操作的强大库。dynamic_bitset 类用于表示 0(复位)或 1(设置)形式的一组位。dynamic_bitset 是对 bitset([**STD::bit set**](https://www.geeksforgeeks.org/c-bitset-and-its-application/)和 **boost::bitset** )的改进，后者在运行时分配任何所需长度的位，而 bit set 的位长度必须在编译时确定。
升压标题**下的**动态位组**升压/动态位组. hpp** 。

**语法:**

```cpp
boost::dynamic_bitset <uint8_t> B (N, num);
```

构造函数的参数是

*   **N** 表示集合中所需的位数。
*   **num** 表示其位将被存储的任何整数值。
*   **uint8_t** 表示块大小(这里是 8，如果不需要指定块大小也可以为空)。

dynamic_bitset 的每个独立位都可以像 bitset 索引运算符[]一样进行访问。
**请注意**长度为 n 的 dynamic_bitset 中数字 B 的比特表示表示为:

```cpp
B[n-1] B[n-2] ... B[1] B[0]
```

换句话说，dynamic_bitset 中的索引以相反的顺序工作(类似于 bitset)。dynamic_bitset 中的每个位都恰好占用 1 位空间，这是因为它进行了优化，因此运算速度比布尔向量快。
**成员函数:**
可以在 dynamic_bitset 上执行的基本成员函数如下:

*   **set()** :它为每个位分配 1
*   **reset()** :如果参数中传递了 n，它会将第 n 个<sup>位</sup>指定为 0，否则它会清除整个位集对象。
*   **翻转()**:它反转任何给定的位，即从 0 切换到 1，反之亦然
*   **size()** :返回 dynamic_bitset 对象的大小
*   **resize()** :用于增加或减少对象的大小
*   **push_back()** :将 dynamic_bitset 对象的大小增加 1，并在 MSB 处推送值
*   **pop_back()** :从 MSB 中删除一位
*   **num_blocks()** :返回位集中的块数
*   **追加**:追加最高有效位的位。这将位集的大小增加了每块位。对于范围[0，bits _ per _ block 中的 I，位置(大小+ i)处的位被设置为((值> > i) & 1)
*   **empty()** :如果 dynamic_bitset 的长度为 0，则返回 true，否则返回 false。
*   **count()** :返回 dynamic_bitset 中设置的位数。
*   **all()** :测试 dynamic_bitset 中的所有位是否都置位，如果都置位，则返回 true，否则返回 false。
*   **any()** :测试 dynamic_bitset 中是否至少设置了一个位，如果设置了，则返回 true，否则返回 false。
*   **none()** :测试 dynamic_bitset 中是否没有设置位，如果没有设置，则返回 true，否则返回 false。
*   **测试()**:测试第 i <sup>位</sup>是否置位。如果设置为 true，则返回 false。

**例 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <boost/dynamic_bitset.hpp>
#include <iostream>

using namespace std;

int main(int argc, char* argv[])
{
    int bit_size = 8;

    // B1 is initialized with size 0
    // with all bits 0
    boost::dynamic_bitset<> B1;

    // B2 is initialized with size
    // bit_size with all bits 0
    boost::dynamic_bitset<> B2(bit_size);

    // B3 is initialized with size
    // bit_size and value 14
    boost::dynamic_bitset<> B3(bit_size, 14);

    // B4 is initialized with size
    // bit_size, value 14 and
    // block_size of 8 bits
    boost::dynamic_bitset<uint8_t> B4(16, 84);

    // Empty
    cout << "Content of B1 is: "
         << B1 << endl;

    // 00000000
    cout << "Content of B2 is: "
         << B2 << endl;
    cout << "Binary representation of 14 in 8 bit: "
         << B3 << endl;
    cout << "Content of B4 is: "
         << B4 << endl
         << endl;

    // Setting 1 st of B2 to 1
    cout << "Content of B2 before set(): "
         << B2 << endl;

    B2.set(0);
    cout << "Content of B2 after set(0): "
         << B2 << endl;

    // Setting every bits of B22 to 1
    B2.set();
    cout << "Content of B2 after set(): "
         << B2 << endl;

    // Resetting 2nd bit to 0
    B2.reset(1);
    cout << "After resetting 2nd bit of B2: "
         << B2<< endl;

    // Resetting every bit to 0
    B2.reset();
    cout << "After resetting every bit of B2: "
         << B2 << endl;

    // Flipping first bit of B3
    cout << "Content of B3 before flip(): "
         << B3 << endl;

    B3.flip(0);
    cout << "Content of B3 after flip(0): "
         << B3 << endl;

    // Flipping every bits of B3
    B3.flip();
    cout << "Content of B3 after flip():  "
         << B3 << endl
         << endl;

    // Size of B1, B2, B3, B4
    cout << "Size of B1 is: "
         << B1.size() << endl;
    cout << "Size of B2 is: "
         << B2.size() << endl;
    cout << "Size of B3 is: "
         << B3.size() << endl;
    cout << "Size of B4 is: "
         << B4.size() << endl
         << endl;

    // Resizing B1 to size 4,
    // default bit-value 0
    B1.resize(4);
    cout << "B1 after increasing size to 4 bits: "
         << B1 << endl;

    // Resizing B1 to size 8, bit-value 1.
    // If num_bits > size() then the bits
    // in the range [0, size()) remain the same,
    // and the bits in [size(), num_bits)
    // are all set to value (here 1).
    B1.resize(8, 1);
    cout << "B1 after increasing size to 8 bits: "
         << B1 << endl;

    // Resizing B1 to size 1 i.e.
    // slicing [1, B1.size()-1)
    B1.resize(1);
    cout << "B1 after decreasing size to 1 bit:  "
         << B1 << endl
         << endl;

    // Pushing a set bit at MSB in B1
    B1.push_back(1);
    cout << "B1 after push(1) operation:   "
         << B1 << endl;

    // Pushing a reset bit at MSB in B1
    B1.push_back(0);
    cout << "B1 after push(0) operation : "
         << B1 << endl
         << endl;

    // Poping 1 bit from MSB in B1
    cout << "B1 before pop operation: "
         << B1 << endl;

    B1.pop_back();
    cout << "B1 after pop operation:   "
         << B1 << endl
         << endl;

    // Number of blocks = number of bits / block size
    cout << "Number of blocks in B4: "
         << B4.num_blocks() << endl
         << endl;

    // Checking if any bitset is empty
    cout << "B1 is "
         << (B1.empty() ? "empty" : "not empty")
         << endl;
    cout << "B2 is "
         << (B2.empty() ? "empty" : "not empty")
         << endl;

    // Resizing B3 to 0
    B3.resize(0);
    cout << "B3 is "
         << (B3.empty() ? "empty" : "not empty")
         << endl
         << endl;

    // Counting number of set bits in B4
    cout << "Content of B4 is: " << B4 << endl;
    cout << "Number of set bits in it are: "
         << B4.count() << endl
         << endl;

    // Checking if all of the bits of B2 is set
    B2.set(); // B2 => 11111111

    cout << "All bits in B2 are "
         << (B2.all() ? "set" : "not set") << endl;

    B2.reset(2); // B2 => 11111011
    cout << "All bits in B2 are "
         << (B2.all() ? "set" : "not set")
         << endl
         << endl;

    // Checking if any of the bits of B2 is set
    cout << (B2.any() ? "Atleast one" : "No")
         << " bit in B2 is set " << endl;
    B2.reset(); // B2 => 00000000

    cout << (B2.any() ? "Atleast one" : "No")
         << " bit in B2 is set " << endl
         << endl;

    // Checking if none of the bits of B2 are set
    // B2 => 00000000
    if (B2.none())
        cout << "None of the bits in B2 is set";
    else
        cout << "Atleast one bit in B2 is set";
    cout << endl
         << endl;

    // Testing if 1st bit of B1 is set or not
    cout << "Content of B1 is: " << B1 << endl;
    if (B1.test(1))
        cout << "B1[1] is set";
    else
        cout << "B1[1] is reset";
    return 0;
}
```

**Output:** 

```cpp
Content of B1 is: 
Content of B2 is: 00000000
Binary representation of 14 in 8 bit: 00001110
Content of B4 is: 0000000001010100

Content of B2 before set(): 00000000
Content of B2 after set(0): 00000001
Content of B2 after set(): 11111111
After resetting 2nd bit of B2: 11111101
After resetting every bit of B2: 00000000
Content of B3 before flip(): 00001110
Content of B3 after flip(0): 00001111
Content of B3 after flip():  11110000

Size of B1 is: 0
Size of B2 is: 8
Size of B3 is: 8
Size of B4 is: 16

B1 after increasing size to 4 bits: 0000
B1 after increasing size to 8 bits: 11110000
B1 after decreasing size to 1 bit:  0

B1 after push(1) operation:   10
B1 after push(0) operation : 010

B1 before pop operation: 010
B1 after pop operation:   10

Number of blocks in B4: 2

B1 is not empty
B2 is not empty
B3 is empty

Content of B4 is: 0000000001010100
Number of set bits in it are: 3

All bits in B2 are set
All bits in B2 are not set

Atleast one bit in B2 is set 
No bit in B2 is set 

None of the bits in B2 is set

Content of B1 is: 10
B1[1] is set
```

**运算符:**
一些有助于位操作的运算符:

*   **运算符[]** :返回第 n <sup>位的引用。</sup>
*   **运算符& =()** :对参数中传递的当前位集对象和位集对象进行按位“与”运算。操作员&=(B2)；B1 和 B2 的按位“与”，即 B1 & B2 (B1 和 B2 必须具有相同的位数)。
*   **运算符|=()** :对参数中传递的当前位集对象和位集对象进行按位“或”运算。例如 B1 . operator | =(B2)；B1 和 B2 的按位“或”，即 B1 | B2 (B1 和 B2 必须具有相同的位数)。
*   **operator^=()** :它对参数中传递的当前位集对象和位集对象进行按位异或运算。例如 b1.operator^=(b2)；B1 和 B2 的逐位异或，即 B1 ^ B2 (B1 和 B2 必须具有相同的位数)。
*   **运算符-=()** :与参数中传递的当前位集对象和位集对象执行集合差运算。操作员-=(B2)；设置 B1 和 B2 的差值，即 B1–B2(B1 和 B2 必须具有相同的位数)。
*   **运算符=()** :用传入参数的对象分配当前位集对象。
*   **运算符==()** :验证当前位集对象是否与作为参数传递的对象完全相同。
*   **符！=()** :验证当前位集对象是否不等于作为参数传递的对象。
*   **运算符< ()** :如果当前位集在字典序上小于作为参数传递的 bitet 对象，则返回真，否则返回假。
*   **运算符> ()** :如果当前位集在字典序上大于作为参数传递的 bitet 对象，则返回真，否则返回假。
*   **运算符< =()** :如果当前位集在字典序上小于或等于作为参数传递的 bitet 对象，则返回真，否则返回假。
*   **运算符> =()** :如果当前位集在字典序上大于或等于作为参数传递的 bitet 对象，则返回真，否则返回假。
*   **运算符~()** :它创建当前位集的副本，其所有位都被翻转。
*   **操作符< < ()** :创建当前位集对象的一个拷贝，该拷贝左移 n 位。
*   **操作符> > ()** :创建当前位集对象的一个拷贝，向右移动 n 位。
*   **运算符< < =()** :将当前位集对象左移 n 位。
*   **运算符> > =()** :将当前位组对象向右移动 n 位。

**例 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <boost/dynamic_bitset.hpp>
#include <iostream>
using namespace std;

int main(int argc, char* argv[])
{
    int n_bits = 8;

    boost::dynamic_bitset<> B1(n_bits, 123);
    boost::dynamic_bitset<> B2(n_bits, 206);
    boost::dynamic_bitset<> temp(4, 3);

    cout << "Binary representation of 123: "
         << B1 << endl;
    cout << "Binary representation of 206: "
         << B2 << endl
         << endl;

    // Operator[] is used to access an individual index
    // It is a reference of the nth bit. It can be used for
    // assignment of a boolean value at nth bit
    cout << "4th bit of B1 consist: "
         << B1[3] << endl;
    B1[3] = 0;
    cout << "Assigning 0 to 4th bit of B1: "
         << B1 << endl
         << endl;

    // Operator= assigns on current bitset object
    cout << "temp before assignment: "
         << temp << endl;

    temp.operator=(B1);
    cout << "temp after assignment with B1: "
         << temp << endl
         << endl;

    // Operator&= performs bitwise-AND
    cout << "B1 consist of: "
         << B1 << endl;
    cout << "B2 consist of: "
         << B2 << endl;

    temp.operator=(B1);
    temp.operator&=(B2);
    cout << "B1 AND B2 is : & "
         << temp << endl
         << endl;

    // Operator|= performs bitwise-OR
    cout << "B1 consist of: "
         << B1 << endl;
    cout << "B2 consist of: "
         << B2 << endl;

    temp.operator=(B1);
    temp.operator|=(B2);
    cout << "B1 OR B2 is  : | "
         << temp << endl
         << endl;

    // Operator^= performs bitwise-XOR
    cout << "B1 consist of: "
         << B1 << endl;
    cout << "B2 consist of: "
         << B2 << endl;

    temp.operator=(B1);
    temp.operator^=(B2);
    cout << "B1 XOR B2 is : ^ "
         << temp << endl
         << endl;

    // Operator-= performs set difference
    cout << "B1 consist of: "
         << B1 << endl;
    cout << "B2 consist of: "
         << B2 << endl;

    temp.operator=(B1);
    temp.operator-=(B2);
    cout << "Set differ is:   "
         << temp << endl
         << endl;

    // Operator== checks if bitset object is equal to
    // another one, bit length has to be same for true
    cout << "dynamic_bitset B1 and B2 are "
         << (operator==(B1, B2) ? "equal" : "not equal")
         << endl;

    boost::dynamic_bitset<> B3(2, 0), B4(3, 0);
    cout << "Content of B3: " << B3 << endl
         << "Content of B4: " << B4 << endl
         << "dynamic_bitset B3 and B4 are "
         << (operator==(B3, B4) ? "equal" : "not equal")
         << endl;

    B3.operator=(B4);
    cout << "dynamic_bitset B3 and B4 are: "
         << (operator==(B3, B4) ? "equal" : "not equal")
         << endl
         << endl;

    // Operator!= checks if bitset object is unequal
    cout << "dynamic_bitset B1 and B2 are ";
    cout << (operator!=(B1, B2) ? "not equal" : "equal")
         << endl
         << endl;

    // Operator< checks if first bitset object is
    // lexicographically less than second one
    cout << "B1 consist of: " << B1 << endl;
    cout << "B2 consist of: " << B2 << endl;

    if (operator<(B1, B2))
        cout << "B1 is lexicographically less than B2";
    else
        cout << "B2 is lexicographically greater than B2";
    cout << endl
         << endl;

    // Operator> checks if first bitset object is
    // lexicographically greater than second one
    cout << "B1 consist of: " << B1 << endl;
    boost::dynamic_bitset<> B5(8, 0);
    cout << "B5 consist of: " << B5 << endl;

    if (operator>(B1, B5))
        cout << "B1 is lexicographically greater than B5";
    else
        cout << "B1 is lexicographically less than B5";
    cout << endl
         << endl;

    // Operator<= checks if first bitset object is
    // lexicographically less than or equal to second one
    cout << "B3 is lexicographically ";
    if (operator<=(B3, B3))
        cout << "less than or equal to B3"
             << endl
             << endl;
    else
        cout << "greater than B3"
             << endl
             << endl;

    // Operator>=
    cout << "B5 consist of: " << B5 << endl;
    cout << "B2 consist of: " << B2 << endl;
    cout << "B5 is lexicographically ";
    if (operator>=(B5, B2))
        cout << "greater than or equal to B2";
    else
        cout << "less than B2";
    cout << endl
         << endl;

    // Operator~ creates a copy of flipped bitset object
    cout << "Value of dynamic_bitset B4 : " << B4 << endl;
    cout << "Creating flipped copy of B4: ";
    cout << B4.operator~() << endl
         << endl;

    // Operator<< creates a copy of current bitset object
    // which is shifted to left by n times
    cout << "Value of dynamic_bitset B2: " << B2 << endl;
    cout << "Copy of B2 left shift 3 times is  : ";
    cout << B2.operator<<(3) << endl;

    // Operator>> creates a copy of current bitset object
    // which is shifted to right by n times value of B2
    // is not changed, the copy is displayed
    cout << "Copy of B2 right shift 1 time is  : ";
    cout << B2.operator>>(1) << endl
         << endl;

    // Operator<<= shifts the current bitset object
    // n times to left
    cout << "Value of dynamic_bitset B2: "
         << B2 << endl;
    cout << "B2 left shift 3 times is  : ";
    cout << B2.operator<<=(2) << endl;

    // Operator>>= shifts current bitset object
    // n times value to right
    cout << "B2 right shift 1 time is  : ";
    cout << B2.operator>>=(3);

    return 0;
}
```

**Output:** 

```cpp
Binary representation of 123: 01111011
Binary representation of 206: 11001110

4th bit of B1 consist: 1
Assigning 0 to 4th bit of B1: 01110011

temp before assignment: 0011
temp after assignment with B1: 01110011

B1 consist of: 01110011
B2 consist of: 11001110
B1 AND B2 is : & 01000010

B1 consist of: 01110011
B2 consist of: 11001110
B1 OR B2 is  : | 11111111

B1 consist of: 01110011
B2 consist of: 11001110
B1 XOR B2 is : ^ 10111101

B1 consist of: 01110011
B2 consist of: 11001110
Set differ is:   00110001

dynamic_bitset B1 and B2 are not equal
Content of B3: 00
Content of B4: 000
dynamic_bitset B3 and B4 are not equal
dynamic_bitset B3 and B4 are: equal

dynamic_bitset B1 and B2 are not equal

B1 consist of: 01110011
B2 consist of: 11001110
B1 is lexicographically less than B2

B1 consist of: 01110011
B5 consist of: 00000000
B1 is lexicographically greater than B5

B3 is lexicographically less than or equal to B3

B5 consist of: 00000000
B2 consist of: 11001110
B5 is lexicographically less than B2

Value of dynamic_bitset B4 : 000
Creating flipped copy of B4: 111

Value of dynamic_bitset B2: 11001110
Copy of B2 left shift 3 times is  : 01110000
Copy of B2 right shift 1 time is  : 01100111

Value of dynamic_bitset B2: 11001110
B2 left shift 3 times is  : 00111000
B2 right shift 1 time is  : 00000111
```

**应用:**

*   dynamic_bitset 可以有效地用来表示有限集合的子集。每一位表示有限集合的元素是否在子集内。
*   [厄拉多塞筛](https://www.geeksforgeeks.org/sieve-of-eratosthenes/)寻找整数 n 以下的所有素数

**参考:**[https://www . boost . org/doc/libs/1 _ 36 _ 0/libs/dynamic _ bitset/dynamic _ bitset . html](https://www.boost.org/doc/libs/1_36_0/libs/dynamic_bitset/dynamic_bitset.html)