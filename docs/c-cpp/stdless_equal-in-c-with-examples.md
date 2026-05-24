# 标准::C++ 中的 less_equal，示例

> 原文:[https://www . geesforgeks . org/stdless _ equal-in-c-with-examples/](https://www.geeksforgeeks.org/stdless_equal-in-c-with-examples/)

**std::less_equals** 是用于执行比较的函数对象类。它被定义为小于相等比较的函数对象类，根据条件返回一个 [**布尔值**](https://www.geeksforgeeks.org/bool-data-type-in-c/) 。它可以与各种标准算法一起使用，如排序、[下界](https://www.geeksforgeeks.org/upper_bound-and-lower_bound-for-vector-in-cpp-stl/)和[容器](https://www.geeksforgeeks.org/containers-cpp-stl/)如[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)、[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)等。

**头文件:**

```cpp
#include <functional.h>

```

**模板类:**

```cpp
template <class T> struct less_equal {

  // Declaration of the 
  // less equal operation 
  bool operator() (const T& x,
                   const T& y) 
      const 
  {
     return x<=y;
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
std::bind2nd(std::less_equal(), K)

```

**参数:**该函数接受参数 **T** 的类型作为参数，由函数调用进行比较。

**返回类型:**根据条件返回一个 [**布尔值**](https://www.geeksforgeeks.org/bool-data-type-in-c/) (让 a & b 为 2 个元素):

*   **True:** If a is less than or equal to b 。
*   **False:** If a is greater than B. 。

下面是 C++ 中 **std::less_equal** 的图示:

**程序 1:**

```cpp
// C++ program to illustrate less_equal
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

    // Sort the array in increasing order
    sort(arr, arr + N, less_equal<int>());

    // Print sorted array
    printArray(arr, N);
    return 0;
}
```

**输出:**

```cpp
0 1 2 3 4 5 6 7 8 9

```

**程序二:**

```cpp
// C++ program to illustrate less_equal
#include <functional>
#include <iostream>
#include <iterator>
#include <set>
using namespace std;

// Driver Code
int main()
{
    // Initialise set with less_equal to
    // store the elements in increasing
    // order
    set<int, less_equal<int> > S;

    // Insert elements in S
    S.insert(75);
    S.insert(30);
    S.insert(60);
    S.insert(20);
    S.insert(50);
    S.insert(30);

    // Print the elements stored in set S
    for (auto& it : S) {
        cout << it << ' ';
    }

    return 0;
}
```

**输出:**

```cpp
20 30 30 50 60 75

```

**参考:**T2】http://www.cplusplus.com/reference/functional/less_equal/