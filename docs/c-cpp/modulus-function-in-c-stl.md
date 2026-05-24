# c++ STL 中的模数函数

> 原文:[https://www.geeksforgeeks.org/modulus-function-in-c-stl/](https://www.geeksforgeeks.org/modulus-function-in-c-stl/)

**模数函数**用于返回其两个自变量之间的模值。它的工作原理与模数运算符相同。

```cpp
template  struct modulus : binary_function  
{
  T operator() (const T& x, const T& y) const 
  {
   return x%y;
  }
};

```

**成员类型:**

*   第一个参数的类型
*   第二个参数的类型
*   成员运算符返回的结果类型

**注意:**我们必须包含库‘泛函’和‘算法’才能使用模数和[变换](https://www.geeksforgeeks.org/transform-c-stl-perform-operation-elements/)。

Bewlo 程序说明了模数函数的工作原理:

```cpp
// C++ program to implement modulus function
#include <algorithm> // transform
#include <functional> // modulus, bind2nd
#include <iostream> // cout
using namespace std;

int main()
{
    // defining the array
    int array[] = { 8, 6, 3, 4, 1 };

    int remainders[5];

    // transform function that helps to apply
    // modulus between the arguments
    transform(array, array + 5, remainders,
              bind2nd(modulus<int>(), 2));

    for (int i = 0; i < 5; i++)
        // printing the results while checking
        // whether no. is even or odd
        cout << array[i] << " is a "
             << (remainders[i] == 0 ? "even" : "odd")
             << endl;

    return 0;
}
```

**Output:**

```cpp
8 is a even
6 is a even
3 is a odd
4 is a even
1 is a odd

```

```cpp
// C++ program to implement modulus function
#include <algorithm> // transform
#include <functional> // modulus, bind2nd
#include <iostream> // cout
#include <iterator>
#include <vector>
using namespace std;

int main()
{

    // Create a std::vector with elements
    // {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}
    vector<int> v;
    for (int i = 0; i < 10; ++ i)
        v.push_back(i);

    // Perform a modulus of two on every element
    transform(v.begin(), v.end(), v.begin(),
              bind2nd(modulus<int>(), 2));

    // Display the vector
    copy(v.begin(), v.end(),
         ostream_iterator<int>(cout, " "));
    cout << endl;

    return 0;
}
```

**Output:**

```cpp
0 1 0 1 0 1 0 1 0 1

```