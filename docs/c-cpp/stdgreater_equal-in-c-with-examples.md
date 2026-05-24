# 标准::C++ 中的大于等于，示例

> 原文:[https://www . geesforgeks . org/STD greater _ equal-in-c-with-examples/](https://www.geeksforgeeks.org/stdgreater_equal-in-c-with-examples/)

**std::greater_equal** 是**功能类(< functional.h > )** 的成员。用于生成类似于运算符 **(≥)** 的比较结果。此函数相对于运算符 **(≥)** 的优势在于，它使用严格的总顺序来生成结果，而运算符 **(≥)** 则使用部分顺序。它根据条件返回一个布尔值。它可以用来比较整数、字符或字符串等。

**头文件:**

```cpp
#include <functional.h>

```

**模板类:**

```cpp
template <class T> struct greater_equal {

  // Declaration of the
  // greater equal operation 
  bool operator() (const T& x, const T& y) 
       const 
  {
      return x>=y;
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

**参数:**该函数接受参数 **T** 的类型作为参数，由函数调用进行比较。

**返回类型:**根据条件返回一个 [**布尔值**](https://www.geeksforgeeks.org/bool-data-type-in-c/) (让 a & b 为 2 个元素):

*   **True:** If a is greater than or equal to B. 。
*   **False:** If a is less than b 。

下面是 C++ 中 **std::大于 _ 等于**的图示:

**程序 1:**

```cpp
// C++ program to illustrate greater_equal

#include <algorithm>
#include <functional>
#include <iostream>
using namespace std;

// Function to print the array arr[]
void printArray(int arr[], int N)
{

    for (int i = 0; i < N; i++) {
        cout << arr[i] << ' ';
    }
}

// Driver Code
int main()
{
    int arr[] = { 1, 5, 8, 9, 6,
                  7, 3, 4, 2, 0 };

    int N = sizeof(arr) / sizeof(arr[0]);

    // Sort the array in decreasing order
    sort(arr, arr + N, greater_equal<int>());

    // Print sorted array
    printArray(arr, N);
    return 0;
}
```

**输出:**

```cpp
9 8 7 6 5 4 3 2 1 0

```

**程序二:**

```cpp
// C++ program to illustrate greater_equal

#include <algorithm>
#include <functional>
#include <iostream>
using namespace std;

// Driver Code
int main()
{

    int arr[] = { 30, 40, -50, 60, -70,
                  10, 20, -80, 90, 100 };
    int N = sizeof(arr) / sizeof(arr[0]);

    // Print the number of elements less
    // than 0
    cout << count_if(
        arr, arr + N,
        bind2nd(greater_equal<int>(),
                0));
    return 0;
}
```

**输出:**

```cpp
7

```

**参考:**T2【http://www . cplusplus . com/Reference/functional/great _ equal/