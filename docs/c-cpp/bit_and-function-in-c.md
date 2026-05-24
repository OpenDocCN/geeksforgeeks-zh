# c++ 中的 bit_and 函数

> 原文:[https://www.geeksforgeeks.org/bit_and-function-in-c/](https://www.geeksforgeeks.org/bit_and-function-in-c/)

**bit_and** 是 C++ 中的一个内置函数，用于在其参数上应用按位 and 后返回值(由运算符&返回)。

```cpp
template  struct bit_and 
{
  T operator() (const T& a, const T& b) const {return a&b;}
  typedef T type of first_argument;
  typedef T type of second_argument;
  typedef T result_type;
};

```

**T** 是所有参数的类型。

**注:**

1.  这个类的对象可以在标准算法上使用，如[变换](https://www.geeksforgeeks.org/transform-c-stl-perform-operation-elements/)或累加。
2.  成员函数(' operator()')返回其参数的**位 _and** 。

我们必须包含库“函数”和“算法”来分别使用 bit_and 和 transform，否则它们将不起作用。

下面是显示**bit _ 和**功能工作的程序:
**程序-1:**

```cpp
// C++ program to show the 
// functionality of bit_and
#include <algorithm> // transform
#include <functional> // bit_and
#include <iostream> // cout
#include <iterator> // end
using namespace std;

int main()
{
    // declaring the values
    int xyz[] = { 500, 600, 300, 800, 200 };
    int abc[] = { 0xf, 0xf, 0xf, 255, 255 };
    int n = 5;
    // defining results
    int results[n];

    // transform is used to apply
    // bitwise_and on the arguments
    transform(xyz, end(xyz), abc,
              results, bit_and<int>());

    // printing the resulting array
    cout << "Results:";
    for (const int& x : results)
        cout << ' ' << x;

    return 0;
}
```

**Output:**

```cpp
Results: 4 8 12 32 200

```

**程序-2:**

```cpp
// C++ program to show the 
// functionality of bit_and
#include <algorithm> // transform
#include <functional> // bit_and
#include <iostream> // cout
#include <iterator> // end
using namespace std;

int main()
{
    // declaring the values
    int xyz[] = { 0, 1100 };
    int abc[] = { 0xf, 0xf };

    // defining results
    int results[2];
    // transform is used to apply
    // bitwise_and on the arguments
    transform(xyz, end(xyz), abc,
              results, bit_and<int>());

    // printing the resulting array
    cout << "Results:";
    for (const int& x : results)
        cout << ' ' << x;

    return 0;
}
```

**Output:**

```cpp
Results: 0 12

```