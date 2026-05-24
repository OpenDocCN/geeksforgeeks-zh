# 标准::C++ 中的 not_equal_to，示例

> 原文:[https://www . geesforgeks . org/stdnot _ equal _ in-c-with-examples/](https://www.geeksforgeeks.org/stdnot_equal_to-in-c-with-examples/)

**std::not_equal_to** 是一个用于**非等式**比较和二元函数对象类的函数对象类。它根据两个参数是否相等的条件返回一个 [**布尔值**](https://www.geeksforgeeks.org/bool-data-type-in-c/) 。
**头文件:**

```cpp
#include <functional.h>
```

**模板类:**

```cpp
template struct not_equal_to :
            binary_function  {

  // Declaration of the
  // not equal to operation 
  bool operator() (const T& x,
                   const T& y) 
       const 
  {
     return x!=y;
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
std::not_equal_to <int> ()
```

**参数:**该函数接受参数 **T** 的类型作为参数，由函数调用进行比较。
**返回类型:**它根据条件返回一个 [**布尔值**](https://www.geeksforgeeks.org/bool-data-type-in-c/) (假设 a & b 是 2 个元素):

*   **真:**如果 a 不等于 b。
*   **假:**如果 a 等于 b。

下面是 C++ 中**STD::not _ equal _ to**:
**程序 1:**
的图解

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to illustrate std::not_equal_to

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
    // search first match between
    // v1 and v2
    pairs1 = mismatch(v1.begin(), v1.end(),
                      v2.begin(),
                      not_equal_to<int>());

    // Print the match pair
    cout << "The 1st match element"
         << " of 1st container : ";
    cout << *pairs1.first << endl;

    cout << "The 1st match element "
         << "of 2nd container : ";
    cout << *pairs1.second << endl;

    return 0;
}
```

**Output:** 

```cpp
The 1st match element of 1st container : 50
The 1st match element of 2nd container : 50
```

**节目 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate
// std::not_equals_to
#include <algorithm>
#include <functional>
#include <iostream>
using namespace std;

// Template
template <typename A, typename B,
          typename U = not_equal_to<int> >

// Function to check if a != b or not
bool f(A a, B b, U u = U())
{
    return u(a, b);
}

// Driver Code
int main()
{
    int X = 1, Y = 2;

    // If X is not equals to Y or not
    cout << boolalpha;
    cout << f(X, Y) << '\n';

    X = -1, Y = -1;

    // If X is not equals to Y or not
    cout << f(X, Y) << '\n';

    return 0;
}
```

**Output:** 

```cpp
true
false
```

**参考:**T2http://www.cplusplus.com/reference/functional/not_equal_to/