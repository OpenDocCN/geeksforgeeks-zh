# 标准::在 C++ 中等于 _ 带示例

> 原文:[https://www . geesforgeks . org/stdequal _ to-in-c-with-examples/](https://www.geeksforgeeks.org/stdequal_to-in-c-with-examples/)

**std::equal_to** 允许将相等比较用作函数，这意味着它可以作为参数传递给模板和函数。这对于等式运算符 **==** 是不可能的，因为运算符不能作为参数传递。
**头文件:**

```cpp
#include <functional.h>
```

**模板类:**

```cpp
template struct equal_to : binary_function
{

  // Declaration of the equal operation
  bool operator() (const T& x,
                   const T& y) 
       const 
  { 
     return x==y;
  }

  // Type of first parameter
  typedef T first_argument_type;

  // Type of second parameter
  typedef T second_argument_type;

  // The result is returned
  // as bool type
  typedef bool result_type;
}
```

**语法:**

```cpp
std::equal_to <int> ()
```

**参数:**该函数接受参数 **T** 的类型作为参数，由函数调用进行比较。
**返回类型:**根据条件返回一个[布尔值](https://www.geeksforgeeks.org/bool-data-type-in-c/)(假设 a & b 是 2 个元素):

*   **真:**如果 a 等于 b。
*   **假:**如果 a 不等于 b。

下图是 C++ 中**STD::equal _ to**:
**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to illustrate std::equal_to
#include <algorithm>
#include <functional>
#include <iostream>
#include <vector>
using namespace std;

// Driver Code
int main()
{
    // Initialise vectors
    vector<int> v1 = { 50, 55, 60,
                       65, 70 };
    vector<int> v2 = { 50, 55, 85,
                       65, 70 };

    // Declaring pointer of pairs
    pair<vector<int>::iterator,
         vector<int>::iterator>
        pairs1;

    // Use mismatch() function to
    // search first mismatch between
    // v1 and v2
    pairs1 = mismatch(v1.begin(), v1.end(),
                      v2.begin(),
                      equal_to<int>());

    // Print the mismatch pair
    cout << "The 1st mismatch element"
         << " of 1st container : ";
    cout << *pairs1.first << endl;

    cout << "The 1st mismatch element"
         << " of 2nd container : ";
    cout << *pairs1.second << endl;

    return 0;
}
```

**Output:** 

```cpp
The 1st mismatch element of 1st container : 60
The 1st mismatch element of 2nd container : 85
```

**节目 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate std::equals_to
#include <algorithm>
#include <functional>
#include <iostream>
using namespace std;

// Template
template <typename A, typename B,
          typename U = std::equal_to<int> >

// Function to check if a = b or not
bool f(A a, B b, U u = U())
{
    return u(a, b);
}

// Driver Code
int main()
{
    int X = 1, Y = 2;

    // If X is equals to Y or not
    cout << std::boolalpha;
    cout << f(X, Y) << '\n';

    X = -1, Y = -1;

    // If X is equals to Y or not
    cout << f(X, Y) << '\n';

    return 0;
}
```

**Output:** 

```cpp
false
true
```

**参考:**T2http://www.cplusplus.com/reference/functional/equal_to/