# c++ STL 中向量的映射，示例

> 原文:[https://www . geeksforgeeks . org/c-STL-in-vectors-map-with-examples/](https://www.geeksforgeeks.org/map-of-vectors-in-c-stl-with-examples/)

**[STL 中的映射](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)** 映射是以映射方式存储元素的关联容器。每个元素都有一个键值和一个映射值。没有两个映射值可以具有相同的键值。

**[STL 中的向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)** 向量与动态数组相同，能够在插入或删除元素时自动调整自身大小，其存储由容器自动处理。向量元素被放在连续的存储中，这样就可以使用迭代器访问和遍历它们。

**STL 中的向量图:**向量图在设计复杂的数据结构时非常有效。

**语法:**

```cpp
map<key, vector<datatype>> map_of_vector;
OR
map<vector<datatype>, key> map_of_vector;

```

**例如**:考虑一个简单的问题，我们必须检查一个向量是否被访问。

```cpp
// C++ program to demonstrate
// use of map for vectors

#include <bits/stdc++.h>
using namespace std;

map<vector<int>, int> vis;

// Print True if vector is visited
// or False if not visited
void CheckVisited(vector<int> data)
{
    if (vis.find(data) != vis.end()) {
        cout << "True" << endl;
    }
    else {
        cout << "False" << endl;
    }
}

// Driver code
int main()
{
    // Initializing some vectors
    vector<int> data_1{ 10, 20, 30, 40 };
    vector<int> data_2{ 5, 10, 15 };
    vector<int> data_3{ 1, 3, 5, 7, 9, 11, 13 };

    // Making some vectors as visited
    vis[data_1] = 1;
    vis[data_2] = 1;
    vis[data_3] = 1;

    // checking if these vectors are
    // visited or not
    vector<int> check_1 = { 5, 10, 15 };
    vector<int> check_2 = { 2, 4, 6, 8, 10, 12 };

    CheckVisited(check_1);
    CheckVisited(check_2);

    return 0;
}
```

**Output:**

```cpp
True
False

```