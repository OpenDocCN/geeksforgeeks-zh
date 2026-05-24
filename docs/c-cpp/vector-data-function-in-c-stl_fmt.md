# C++ STL 中的 `vector::data()` 函数

> 原文：`https://www.geeksforgeeks.org/vector-data-function-in-c-stl/`

`std::vector::data()` 是 C++ STL 中的一个函数，它返回一个指向内存数组的直接指针，该数组由 vector 内部使用，用于存储其拥有的元素。

**语法：**

```cpp
vector_name.data()
```

**参数：** 函数不接受任何参数。
**返回值：** 该函数返回指向数组中第一个元素的指针，该指针由向量内部使用。

下面的程序说明了上述功能：

## 示例程序

```cpp
// C++ program to demonstrate the
// vector::data() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialising vector
    vector<int> vec = { 10, 20, 30, 40, 50 };

    // memory pointer pointing to the
    // first element
    int* pos = vec.data();

    // prints the vector
    cout << "The vector elements are: ";
    for (int i = 0; i < vec.size(); ++ i)
        cout << *pos++ << " ";

    return 0;
}
```

**输出**

```
The vector elements are: 10 20 30 40 50
```