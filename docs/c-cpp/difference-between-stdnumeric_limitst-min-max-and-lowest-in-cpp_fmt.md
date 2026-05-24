# std::numeric_limits<T> 中的 min()、max() 和 lowest() 之间的差异

> 原文：[https://www.geeksforgeeks.org/difference-between-stdnumeric_limitst-min-max-and-lowest-in-cpp/](https://www.geeksforgeeks.org/difference-between-stdnumeric_limitst-min-max-and-lowest-in-cpp/)

[`<limits>`](https://www.geeksforgeeks.org/climits-limits-h-cc/) 中的 `std::numeric_limits<T>` 类为所有数值数据类型以及其他[成员函数](https://www.geeksforgeeks.org/const-member-functions-c/)提供了 `min()`、`max()` 和 `lowest()` 函数。

## std::numeric_limits<T>::max()

`std::numeric_limits<T>::max()` 对于任何类型 `T` 给出了数值类型 `T` 所能表示的最大有限值。因此，函数 `max()` 为数据类型 `T` 给出一个值 `x`，这样就没有其他有限值 `y`，其中 `y > x`。

对于整数类型和浮点[数据类型](https://www.geeksforgeeks.org/data-types-in-c/)，函数 `max()` 给出了可以表示的最大值，并且在数字行上没有位于该值右侧的其他值。

## std::numeric_limits<T>::lowest()

任何类型 `T` 的 `std::numeric_limits<T>::lowest()` 是数字类型 `T` 所能表示的最低有限值，因此在 `y > x` 处没有其他有限值 `y`。

对于整数类型和浮点数据类型，函数 `lowest()` 给出了可以表示的最小值，并且在数字行上没有位于该值左侧的其他值。函数 `lowest()` 基本上是 `max()` 的负值。

## std::numeric_limits<T>::min()

`std::numeric_limits<T>::min()` 对于任何类型 `T` 都是数值类型 `T` 所能表示的最小有限值。因此，函数 `min()` 是可以用类型 `T` 表示的最小可能值。

对于非规格化的浮点类型，函数 `min()` 返回最小正规格化值。由于函数 `min()` 返回浮点类型的最小正规范化值，该值的指数不能是 `0`。

要获得最小正反规范值，请使用 `std::numeric_limits<T>::denorm_min()`。`denorm_min()` 仅适用于浮点类型，对于整数类型，它给出 `0`。

对于整数类型，`min()` 函数是 `lowest()` 的别名，这意味着两者给出相同的最低有限值。如果整数值的 `min()` 定义类似于浮点类型，那么该值应该是 `1`。

**例如：**

| 类型 | max() | lowest() | min() |
| :--- | :--- | :--- | :--- |
| int (4字节) | 2147483647 | -2147483648 | -2147483648 |
| float (4字节) | 3.40282e+38 | -3.40282e+38 | 1.17549e-38 |

下面是说明上述概念的程序：

## C++

```cpp
// C++ program to illustrate difference
// between the numeric limits min, max,
// and the lowest

#include <bitset>
#include <iostream>
#include <limits>
using namespace std;

// Driver Code
int main()
{
    int x;

// Size of int
    cout << "int " << sizeof(int)
         << " bytes" << endl;

// numeric_limits<int>::max()
    x = numeric_limits<int>::max();
    cout << "\tmax :" << endl
         << bitset<8 * sizeof(x)>(x)
         << endl
         << x << endl;

// numeric_limits<int>::lowest()
    x = numeric_limits<int>::lowest();
    cout << "\tlowest :" << endl
         << bitset<8 * sizeof(x)>(x)
         << endl
         << x << endl;

// numeric_limits<int>::min()
    x = numeric_limits<int>::min();
    cout << "\tmin :" << endl
         << bitset<8 * sizeof(x)>(x)
         << endl
         << x << endl;

// numeric_limits<int>::denorm_min()
    x = numeric_limits<int>::denorm_min();
    cout << "\tdenorm_min :" << endl
         << bitset<8 * sizeof(x)>(x)
         << endl
         << x << endl;

cout << endl;

// Size of float
    cout << "float " << sizeof(float)
         << " bytes" << endl;
    float f;

// numeric_limits<int>::max()
    f = numeric_limits<float>::max();

// read the binary representation
    // of the float as an integer
    x = *(int*)&f;

cout << "\tmax :" << endl
         << bitset<8 * sizeof(x)>(x)
         << endl
         << f << endl;

// numeric_limits<int>::lowest()
    f = numeric_limits<float>::lowest();
    x = *(int*)&f;

cout << "\tlowest :" << endl
         << bitset<8 * sizeof(x)>(x)
         << endl
         << f << endl;

// numeric_limits<int>::min()
    f = numeric_limits<float>::min();
    x = *(int*)&f;
    cout << "\tmin :" << endl
         << bitset<8 * sizeof(x)>(x)
         << endl
         << f << endl;

// numeric_limits<int>::denorm_min()
    f = numeric_limits<float>::denorm_min();
    x = *(int*)&f;
    cout << "\tdenorm_min :" << endl
         << bitset<8 * sizeof(x)>(x)
         << endl
         << f << endl;

return 0;
}
```

**Output:**

```cpp
int 4 bytes
    max :
01111111111111111111111111111111
2147483647
    lowest :
10000000000000000000000000000000
-2147483648
    min :
10000000000000000000000000000000
-2147483648
    denorm_min :
00000000000000000000000000000000
0

float 4 bytes
    max :
01111111011111111111111111111111
3.40282e+38
    lowest :
11111111011111111111111111111111
-3.40282e+38
    min :
00000000100000000000000000000000
1.17549e-38
    denorm_min :
00000000000000000000000000000001
1.4013e-45
```

**注意：** 在 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 中，默认精度为 `6`，这意味着最多使用 `6` 个有效数字来表示数字，因此，实际数字将与打印值不同。获取实际值以尝试设置更高的精度。

下面是同样的程序来说明：

## C++

```cpp
// C++ program to illustrate the
// above concepts

#include <bitset>
#include <iomanip>
#include <iostream>
#include <limits>
using namespace std;

// Driver Code
int main()
{
    // Output is not exact
    cout << "\tlowest :" << endl
         << numeric_limits<float>::lowest()
         << endl;

// The value from the output
    float f = -3.40282e+38;
    int x = *(int*)&f;
    cout << bitset<8 * sizeof(x)>(x)
         << endl
         << endl;

// Correct value
    f = numeric_limits<float>::lowest();
    x = *(int*)&f;
    cout << "\tnumeric_limits<float>::lowest() :"
         << endl
         << bitset<8 * sizeof(x)>(x)
         << endl
         << endl;

cout << "\tusing setprecision:"
         << endl;

// output is more precise
    cout << setprecision(10) << f << endl;

// The value from the output
    f = -3.402823466e+38;

// Read the binary representation
    // of the float as an integer
    x = *(int*)&f;

cout << bitset<8 * sizeof(x)>(x)
         << endl;

return 0;
}
```

**Output:**

```cpp
lowest :
-3.40282e+38
11111111011111111111111111111111

numeric_limits<float>::lowest() :
11111111011111111111111111111111

using setprecision:
-3.402823466e+38
11111111011111111111111111111111
```