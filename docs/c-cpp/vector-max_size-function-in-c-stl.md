# c++ STL 中的 vector max_size()函数

> 原文:[https://www . geesforgeks . org/vector-max _ size-function-in-c-STL/](https://www.geeksforgeeks.org/vector-max_size-function-in-c-stl/)

**向量::max_size()** 是 C++ STL 中的内置函数，返回向量容器可以容纳的最大元素数量。

**语法:**

```cpp
vector_name.max_size()

```

**参数:**函数不接受任何参数。

**返回值:**函数返回向量容器可以容纳的最大数字。

程序如下图说明了上面的功能:

```cpp
// C++ program to illustrate the
// vector::max_size() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize a vector
    vector<int> vec;

    // returns the max_size of vector
    cout << "max_size of vector 1 = " << vec.max_size() << endl;

    vector<int> vec1;

    // returns the max_size of vector
    cout << "max_size of vector 2 = " << vec1.max_size() << endl;
    return 0;
}
```

**输出:**

```cpp
max_size of vector 1 = 4611686018427387903
max_size of vector 2 = 4611686018427387903

```