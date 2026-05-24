# c++ STL 中向量的向量，示例

> 原文:[https://www . geesforgeks . org/vector-of-vector-in-c-STL-with-examples/](https://www.geeksforgeeks.org/vector-of-vectors-in-c-stl-with-examples/)

**先决条件:**[c++ STL 中的向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)

[](https://www.geeksforgeeks.org/vector-in-cpp-stl/)**向量被称为[动态数组](https://www.geeksforgeeks.org/how-do-dynamic-arrays-work/)，能够在插入或删除元素时自动调整自身大小，其存储由容器自动处理。**

****向量向量**是一个[二维向量](https://www.geeksforgeeks.org/2d-vector-in-cpp-with-user-defined-size/)，每行都是向量，行数可变。向量的每个索引存储一个向量，可以使用[迭代器](https://www.geeksforgeeks.org/iterators-c-stl/)遍历和访问该向量。它类似于 **[向量数组](https://www.geeksforgeeks.org/array-of-vectors-in-c-stl/)** ，但具有动态属性。**

****语法:****

```cpp
vector<vector<data_type>> vec;
```

****示例:****

```cpp
vector<vector<int>> vec{ { 1, 2, 3 }, 
                         { 4, 5, 6 }, 
                         { 7, 8, 9, 4 } }; 
where vec is the vector of vectors with different
      number of elements in different rows 
```

****<u>插入向量的向量中</u>****

**可以使用 C++ STL 的 [**push_back()**](https://www.geeksforgeeks.org/vectorpush_back-vectorpop_back-c-stl/) 功能将元素插入到向量中。**

**下面的例子演示了向量的插入操作。代码使用 push_back()函数创建一个 2D 向量，然后显示矩阵。**

****语法:****

```cpp
vector_name.push_back(value)

where *value* refers to the element
      to be added in the back of the vector 
```

****例 1:****

```cpp
v2 = {1, 2, 3}
v1.push_back(v2); 
```

**该函数将向量 v2 推进向量 v1 的向量中。因此 v1 变成{ {1，2，3} }。**

****例 2:****

```cpp
v2 = {4, 5, 6}
v1.push_back(v2); 
```

**该函数将向量 v2 推入向量 v1 的现有向量中，v1 变为 v1 = { {1，2，3}，{4，5，6} }**

**下面是演示插入向量的例子。**

```cpp
// C++ program to demonstrate insertion
// into a vector of vectors

#include <iostream>
#include <vector>
using namespace std;

// Defining the rows and columns of
// vector of vectors
#define ROW 4
#define COL 5

int main()
{
    // Initializing the vector of vectors
    vector<vector<int> > vec;

    // Elements to insert in column
    int num = 10;

    // Inserting elements into vector
    for (int i = 0; i < ROW; i++) {
        // Vector to store column elements
        vector<int> v1;

        for (int j = 0; j < COL; j++) {
            v1.push_back(num);
            num += 5;
        }

        // Pushing back above 1D vector
        // to create the 2D vector
        vec.push_back(v1);
    }

    // Displaying the 2D vector
    for (int i = 0; i < vec.size(); i++) {
        for (int j = 0; j < vec[i].size(); j++)
            cout << vec[i][j] << " ";
        cout << endl;
    }
    return 0;
}
```

****Output:**

```cpp
10 15 20 25 30 
35 40 45 50 55 
60 65 70 75 80 
85 90 95 100 105

```** 

****<u>向量中的移除或删除</u>****

**可以使用 C++ STL 的 **[pop_back()](https://www.geeksforgeeks.org/vectorpush_back-vectorpop_back-c-stl/)** 函数从向量的向量中移除元素。**

**下面的例子演示了向量中的移除操作。代码使用 pop_back()函数从 2D 向量中移除元素，然后显示矩阵。
**语法:****

```cpp
vector_name[row_position].pop_back()
```

****例 1:** 让向量的向量为向量 v = { { 1，2，3 }，{ 4，5，6 }，{ 7，8，9 } }**

```cpp
v[2].pop_back() 
```

**该函数从最后一行向量中移除元素 9。因此 v 变成了{ { 1，2，3 }，{ 4，5，6 }，{ 7，8 } }。**

****例 2:****

```cpp
v[1].pop_back() 
```

**该函数从最后一个第二行向量中移除元素 6。因此 v 变成了{ { 1，2，3 }，{ 4，5 }，{ 7，8 } }。**

**下面是演示从向量向量中移除的示例。**

```cpp
// C++ program to demonstrate removal
// from a vector of vectors

#include <iostream>
#include <vector>
using namespace std;

// Driver Method
int main()
{
    // Initializing 2D vector "vect" with
    // sample values
    vector<vector<int> > vec{ { 1, 2, 3 },
                              { 4, 5, 6 },
                              { 7, 8, 9 } };

    // Removing elements from the
    // last row of the vector
    vec[2].pop_back();
    vec[1].pop_back();

    // Displaying the 2D vector
    for (int i = 0; i < 3; i++) {
        for (
            auto it = vec[i].begin();
            it != vec[i].end(); it++)
            cout << *it << " ";
        cout << endl;
    }
    return 0;
}
```

****Output:**

```cpp
1 2 3 
4 5 
7 8

```** 

****<u>向量的向量遍历</u>****

**向量的向量可以用 C++ 中的 [**迭代器**](https://www.geeksforgeeks.org/iterators-c-stl/) 遍历。下面的代码演示了 2D 向量的遍历。**

****语法:****

```cpp
for i in [0, n)
{
    for (iterator it = v[i].begin();
         it != v[i].end(); it++) 
   {
        // Operations to be done
        // For example to print
        print(*it)
    }
} 
```

**下面是演示向量中遍历的例子。**

```cpp
// C++ code to demonstrate traversal
// of a 2D vector

#include <iostream>
#include <vector>
using namespace std;

// Driver Method
int main()
{
    // Initializing 2D vector "vect" with
    // sample values
    vector<vector<int> > vec{ { 1, 2, 3 },
                              { 4, 5, 6 },
                              { 7, 8, 9 } };

    // Displaying the 2D vector
    for (int i = 0; i < 3; i++) {
        for (
            auto it = vec[i].begin();
            it != vec[i].end(); it++)
            cout << *it << " ";
        cout << endl;
    }

    return 0;
}
```

****Output:**

```cpp
1 2 3 
4 5 6 
7 8 9

```**