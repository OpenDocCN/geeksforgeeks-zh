# c++ 中 STL 数组上的关系运算符

> 原文:[https://www . geesforgeks . org/relational-operator-on-STL-array-in-c/](https://www.geeksforgeeks.org/relational-operators-on-stl-array-in-c/)

文章说明了不同的关系运算符在[数组 STL](https://www.geeksforgeeks.org/array-class-c/) 上的工作。**等式比较(== )** 通过使用运算符(==)顺序比较元素来执行，在第一个不匹配处停止。
**小于比较(< )** 或**大于比较(> )** 的行为就像使用算法字典式 _ 比较，该算法使用运算符()以倒数方式顺序比较元素(即同时检查 a < b 和 b < a)，并在第一次出现时停止。
关系运算符在数组上的实现帮助我们比较存储在不同数组中的数据。

**等价运算符:**下面是一些工作相同的运算符。

```cpp
  (a != b) is equivalent to !(a == b)
  (a > b) equivalent to (b < a)
  (a <= b) equivalent to !(b < a)  

```

**时间复杂度:**上述运算的时间复杂度为 **O(n)** ，其中 n 为数组的大小。

下面是说明关系运算符在数组上的工作的代码

**程序 1:** 关系运算符比较

```cpp
// array comparisons using relational operators
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // declaration of array
    array<int, 5> a = { 1, 2, 3, 4, 5 };
    array<int, 5> b = { 1, 2, 3, 4, 5 };
    array<int, 5> c = { 5, 4, 3, 2, 1 };

    if (a >= b) {
        cout << "a is greater than equal to b\n";
    }
    else {
        cout << "a is neither greater than nor equal to b\n";
    }

    if (b < c) {
        cout << "b is less than c\n";
    }
    else {
        cout << "b is not lesser than c\n";
    }
    if (a >= c) {
        cout << "a is greater than equal to c\n";
    }
    else {
        cout << "a is neither greater than nor equal to c\n";
    }

    return 0;
}
```

**输出:**

```cpp
a is greater than equal to b
b is less than c
a is neither greater than nor equal to c

```

**程序 2:** 关系运算符等式

```cpp
// CPP program to check for array qualities.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // declaration of array
    array<char, 5> a = { 'a', 'b', 'c', 'd', 'e' };
    array<char, 5> b = { 'e', 'd', 'c', 'b', 'a' };
    array<char, 5> c = { 'a', 'b', 'c', 'd', 'e' };

    if (a == b) {
        cout << "a is  equal to b\n";
    }
    else {
        cout << "a is not equal to b\n";
    }

    if (b != c) {
        cout << "b is not equal to c\n";
    }
    else {
        cout << "b is equal to c\n";
    }
    if (a == c) {
        cout << "a is equal to c\n";
    }
    else {
        cout << "a is not equal to c\n";
    }

    return 0;
}
```

**输出:**

```cpp
a is not equal to b
b is not equal to c
a is equal to c

```