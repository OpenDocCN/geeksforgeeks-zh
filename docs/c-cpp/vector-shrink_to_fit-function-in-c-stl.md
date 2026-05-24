# c++ STL 中的向量收缩到拟合()函数

> 原文:[https://www . geesforgeks . org/vector-shrink _ to _ fit-function-in-c-STL/](https://www.geeksforgeeks.org/vector-shrink_to_fit-function-in-c-stl/)

**向量::shrink_to_fit()** 是 C++ STL 中的一个内置函数，它会减少容器的容量以适合其大小，并销毁超出容量的所有元素。

**语法:**

```cpp
vector_name.shrink_to_fit()

```

**参数:**函数不接受任何参数。

**返回值:**函数不返回任何内容。

下面的程序说明了上面的功能:

```cpp
// C++ program to illustrate
// the vector::shrink_to_fit() 
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Initialized vector
    vector<int> v(10);

    for (int i = 0; i < 10; i++)
        v[i] = i;

    // Initial vector
    cout << "Vector size initially: " << v.size();

    cout << "\nVector elements are: ";
    for (int i = 0; i < 10; i++)
        cout << v[i] << " ";

    // changes the size of the Vector
    // but does not destroys the elements
    v.resize(5);

    cout << "\n\nVector size after resize(5): "
    << v.size();

    cout << "\nVector elements after resize(5) are: ";
    for (int i = 0; i < 10; i++)
        cout << v[i] << " ";

    // Shrinks to the size
    // till which elements are
    // destroys the elements after 5
    v.shrink_to_fit();

    cout << "\n\nVector size after shrink_to_fit(): "
    << v.size();

    cout << "\nVector elements after shrink_to_fit() are: ";
    for (int i = 0; i < 10; i++)
        cout << v[i] << " ";

    return 0;
}
```

**Output:**

```cpp
Vector size initially: 10
Vector elements are: 0 1 2 3 4 5 6 7 8 9 

Vector size after resize(5): 5
Vector elements after resize(5) are: 0 1 2 3 4 5 6 7 8 9 

Vector size after shrink_to_fit(): 5
Vector elements after shrink_to_fit() are: 0 1 2 3 4 0 127889 0 0 0

```