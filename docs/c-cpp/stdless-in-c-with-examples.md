# 标准::C++ 中更少，示例

> 原文:[https://www.geeksforgeeks.org/stdless-in-c-with-examples/](https://www.geeksforgeeks.org/stdless-in-c-with-examples/)

**std::less** 是用于执行比较的**功能类(< functional.h > )** 的成员。它被定义为小于不等式比较的函数对象类，根据条件返回布尔值。这可以用来改变给定功能的功能。它可以与各种标准算法一起使用，如排序、[下界](https://www.geeksforgeeks.org/upper_bound-and-lower_bound-for-vector-in-cpp-stl/)等。

**头文件:**

```cpp
#include <functional.h>

```

**模板类:**

```cpp
template <class T> struct less {

  // Declaration of the less operation
  bool operator() (const T& x,
                   const T& y) 
       const 
  {
     return x  < y;
  }

  // Type of first parameter
  typedef T first_argument_type;

  // Type of second parameter
  typedef T second_argument_type;

  // The result is returned
  // as bool type
  typedef bool result_type;
};

```

**语法:**

```cpp
std::less()

```

**参数:**该函数接受参数 **T** 的类型作为参数，由函数调用进行比较。

**返回类型:**根据条件返回一个 [**布尔值**](https://www.geeksforgeeks.org/bool-data-type-in-c/) (让 a & b 为 2 个元素):

*   **True:** If a is less than b 。
*   **False:** If a is greater than B. 。

下面是 C++ 中 **std::less** 的图解:

**程序 1:**

```cpp
// C++ program to illustrate
// std::less function
#include <algorithm>
#include <functional>
#include <iostream>
using namespace std;

// Function to print array arr[]
void printArray(int arr[], int N)
{

    for (int i = 0; i < N; i++) {
        cout << arr[i] << ' ';
    }
}

// Driver Code
int main()
{
    int arr[] = { 26, 23, 21, 22,
                  28, 27, 25, 24 };

    int N = sizeof(arr) / sizeof(arr[0]);

    // Sort the array in increasing order
    sort(arr, arr + N, less<int>());

    // Print sorted array
    printArray(arr, N);
    return 0;
}
```

**输出:**

```cpp
21 22 23 24 25 26 27 28

```

**程序二:**

```cpp
// C++ program to illustrate less
#include <iostream>
#include <algorithm>
#include <functional>
using namespace std;

// Template
template <typename A, typename B, 
          typename U = std::less<int> >

// Function to check if a < b or not
bool f(A a, B b, U u = U())
{
    return u(a, b);
}

// Driver Code
int main()
{
    int X = 1, Y = 2;

    // If X is less than Y or not
    cout << std::boolalpha;
    cout << f(X, Y) << '\n';

    X = 2, Y = -1;

    // If X is less than Y or not
    cout << f(X, Y) << '\n';

    return 0;
}
```

**输出:**

```cpp
true
false

```

**参考:**T2】http://www.cplusplus.com/reference/functional/less/