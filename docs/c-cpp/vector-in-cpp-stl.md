# c++ STL 中的向量

> 原文:[https://www.geeksforgeeks.org/vector-in-cpp-stl/](https://www.geeksforgeeks.org/vector-in-cpp-stl/)

向量与动态数组相同，能够在插入或删除元素时自动调整自身大小，其存储由容器自动处理。向量元素被放在连续的存储中，这样就可以使用迭代器访问和遍历它们。在向量中，数据被插入到末尾。在末尾插入需要不同的时间，因为有时可能需要扩展数组。移除最后一个元素只需要恒定的时间，因为不会发生调整大小的情况。在开始或中间插入和擦除在时间上是线性的。

与向量相关的某些函数是:
**迭代器**

1.  [begin()](https://www.geeksforgeeks.org/vectorbegin-vectorend-c-stl/)–返回指向向量中第一个元素的迭代器
2.  [end()](https://www.geeksforgeeks.org/vectorbegin-vectorend-c-stl/)–返回一个迭代器，指向向量中最后一个元素之后的理论元素
3.  [rbe gin()](https://www.geeksforgeeks.org/vector-rbegin-and-rend-function-in-c-stl/)–返回指向向量中最后一个元素的反向迭代器(反向开始)。它从最后一个元素移动到第一个元素
4.  [rend()](https://www.geeksforgeeks.org/vector-rbegin-and-rend-function-in-c-stl/)–返回一个反向迭代器，指向向量中第一个元素之前的理论元素(被认为是反向结束)
5.  [CBE gin()](https://www.geeksforgeeks.org/vector-cbegin-vector-cend-c-stl/)–返回指向向量中第一个元素的常量迭代器。
6.  [cend()](https://www.geeksforgeeks.org/vector-cbegin-vector-cend-c-stl/)–返回一个常量迭代器，指向向量中最后一个元素之后的理论元素。
7.  [Cr begin()](https://www.geeksforgeeks.org/vectorcrend-vectorcrbegin-examples/)–返回一个指向向量中最后一个元素的常量反向迭代器(反向开始)。它从最后一个元素移动到第一个元素
8.  [crend()](https://www.geeksforgeeks.org/vectorcrend-vectorcrbegin-examples/)–返回一个常量反向迭代器，指向向量中第一个元素之前的理论元素(视为反向结束)

```cpp
// C++ program to illustrate the
// iterators in vector
#include <iostream>
#include <vector>

using namespace std;

int main()
{
    vector<int> g1;

    for (int i = 1; i <= 5; i++)
        g1.push_back(i);

    cout << "Output of begin and end: ";
    for (auto i = g1.begin(); i != g1.end(); ++ i)
        cout << *i << " ";

    cout << "\nOutput of cbegin and cend: ";
    for (auto i = g1.cbegin(); i != g1.cend(); ++ i)
        cout << *i << " ";

    cout << "\nOutput of rbegin and rend: ";
    for (auto ir = g1.rbegin(); ir != g1.rend(); ++ ir)
        cout << *ir << " ";

    cout << "\nOutput of crbegin and crend : ";
    for (auto ir = g1.crbegin(); ir != g1.crend(); ++ ir)
        cout << *ir << " ";

    return 0;
}
```

**Output:**

```cpp
Output of begin and end: 1 2 3 4 5 
Output of cbegin and cend: 1 2 3 4 5 
Output of rbegin and rend: 5 4 3 2 1 
Output of crbegin and crend : 5 4 3 2 1

```