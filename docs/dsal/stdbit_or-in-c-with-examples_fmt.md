# std::bit_or C++ 示例

> 原文: [https://www.geeksforgeeks.org/stdbit_or-in-c-with-examples/](https://www.geeksforgeeks.org/stdbit_or-in-c-with-examples/)

**位或**是 C++ 中的一个内置函数，用于执行**[位或](https://www.geeksforgeeks.org/bitwise-operators-in-c-cpp/)**，并在其参数上应用**位或**运算后返回结果。

## 头文件

```cpp
#include <functional>
```

## 模板类

```cpp
template <class T> struct bit_or;
```

## 参数

它接受一个参数 `T`，这是函数调用要比较的参数类型。

## 注意

1.  此类的对象可用于标准算法，例如 [transform](https://www.geeksforgeeks.org/transform-c-stl-perform-operation-elements/) 或累加。
2.  该函数 (`operator()`) 返回其参数的**位或**结果。

我们必须包含库 `<functional>` 和 `<algorithm>` 来分别使用 `bit_or` 和 `transform()`。

下面是 C++ 中**位或**的图示:

## 问题 1

```cpp
// C++ program to show the
// functionality of bit_or

#include <algorithm> // to include transform
#include <functional> // to include bit_or
#include <iostream>
#include <iterator>
using namespace std;

int main()
{
    // declaring the values
    int xyz[] = { -7, 2, 5, 100, 1029 };
    int abc[] = { -4, 0, 5, 1, 1 };
    int n = 5;
    // defining results
    int results[n];

    // transform is used to apply
    // bitwise_or on the arguments
    transform(xyz, end(xyz), abc,
              results, bit_or<int>());

    // printing the resulting array
    cout << "Results:";
    for (const int& x : results)
        cout << ' ' << x;

    return 0;
}
```

**输出:**

```
Results: -3 2 5 101 1029
```

> **某些点要记住**
>
> 1.  一个数与**零**进行位或运算，结果是该数本身。
> 2.  两个**相同的数**进行位或运算，结果也等于该数本身。
> 3.  如果一个数是**奇数**，它与 1 进行位或运算将得到相同的数。
> 4.  如果一个数是偶数，它与 1 进行位或运算将总是得到 **"number+1"**。

## 问题 2

```cpp
// C++ program to show the
// functionality of bit_or

#include <algorithm>
#include <functional>
#include <iostream>
#include <iterator>
using namespace std;

int main()
{
    // declaring the values
    // in form of hexadecimals
    int xyz[] = { 0, 1100 };
    int abc[] = { 0xf, 0xf };

    // defining results
    int results[2];

    // transform is used to apply
    // bitwise_or on the arguments
    transform(xyz, end(xyz), abc,
              results, bit_or<int>());

    // printing the resulting array
    cout << "Results:";
    for (const int& x : results)
        cout << ' ' << x;

    return 0;
}
```

**输出:**

```
Results: 15 1103
```

**参考:** [https://en.cppreference.com/w/cpp/utility/functional/bit_or](https://en.cppreference.com/w/cpp/utility/functional/bit_or)