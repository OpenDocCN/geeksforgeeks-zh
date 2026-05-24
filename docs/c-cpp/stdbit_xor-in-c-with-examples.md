# 标准::C++ 中的 bit_xor，示例

> 原文:[https://www . geesforgeks . org/stdbit _ xor-in-c-with-examples/](https://www.geeksforgeeks.org/stdbit_xor-in-c-with-examples/)

**bit_xor** 是 C++ 中的一个内置函数，用于执行 **[bitwise_xor](https://www.geeksforgeeks.org/bitwise-operators-in-c-cpp/)** ，并在其参数上应用 **bitwise_xor** 运算后返回结果。

**头文件:**

```cpp
#include <functional.h>

```

**模板类:**

```cpp
template <class T> struct bit_xor;

```

**参数:**它接受一个参数 **T** ，这是函数调用要比较的参数类型。

**注:**

1.  这个类的对象可以在标准算法上使用，如[变换](https://www.geeksforgeeks.org/transform-c-stl-perform-operation-elements/)或累加。
2.  成员函数(' operator()')返回其参数的**位 _xor** 。

我们必须包含库**“函数”**和**“算法”**来分别使用 bit_xor 和 transform()。

下面是 C++ 中 **bit_xor** 的图解:
**问题 1:**

```cpp
// C++ program to illustrate bit_xor in C++

#include <algorithm>
#include <functional> // to include bit_xor
#include <iostream>
#include <iterator>
using namespace std;

int main()
{
    // declaring the values
    int A[] = { 1, 2, 3, 4, 5, 6 };
    int B[] = { 6, 7, 8, 4, 5, 0 };
    int n = 6;
    // defining result
    int result[n];

    // transform is used to apply bitwise_xor
    // on the arguments A and B
    transform(A, end(A), B,
              result, bit_xor<int>());

    // printing the resulting array
    cout << "A xor B = ";
    for (const int& answer : result)
        cout << ' ' << answer;

    return 0;
}
```

**Output:**

```cpp
A xor B =  7 5 11 0 0 6

```

**程序 2:**

```cpp
// C++ program to illustrate bit_xor in C++

#include <algorithm>
#include <functional>
#include <iostream>
#include <iterator>
using namespace std;

int main()
{
    // declaring the values
    int A[] = { 0, 0xff, 15, 22 };
    int B[] = { 1, 255, 0xfa, 0x16 };
    int n = 4;
    // defining result
    int result[n];

    // transform is used to apply bitwise_xor
    // on the arguments A and B
    transform(A, end(A), B,
              result, bit_xor<int>());

    // printing the resulting array
    cout << "A xor B = ";
    for (const int& answer : result)
        cout << ' ' << answer;

    return 0;
}
```

**Output:**

```cpp
A xor B =  1 0 245 0

```

**参考:**[https://en . cppreference . com/w/CPP/utility/functional/bit _ xor](https://en.cppreference.com/w/cpp/utility/functional/bit_xor)