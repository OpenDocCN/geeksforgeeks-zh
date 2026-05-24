# c++ STL 中的向量列表，带示例

> 原文:[https://www . geesforgeks . org/c-STL-in-vectors-list-with-examples/](https://www.geeksforgeeks.org/list-of-vectors-in-c-stl-with-examples/)

**<u>列出</u>**

[**<u>列表</u>**](https://www.geeksforgeeks.org/list-cpp-stl/) 是允许非连续内存分配的序列容器。与 vector 相比，列表遍历速度慢，但是一旦找到位置，插入和删除就很快。通常，当我们说一个列表时，我们说的是一个双链表。为了实现单链表，我们使用和转发列表。

**与列表一起使用的功能:**

*   **push_front(x):** 在列表的开头添加一个新元素‘x’。
*   **push_back(x):** 在列表末尾添加新元素‘x’。

**<u>转发列表</u>**

[**<u>正向列表</u>**](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/) 在 STL 中实现单链表。前向列表是从 C++ 11 引入的，在插入、移除和移动操作(如排序)方面比其他容器更有用，并且允许元素的时间常数插入和移除。与[<u>列表</u>](https://www.geeksforgeeks.org/list-cpp-stl/) 的不同之处在于前进列表仅跟踪下一个元素的位置，而列表跟踪下一个和上一个元素的，从而增加了存储每个元素所需的存储空间。 a 正向列表的缺点是不能迭代反向，不能直接访问其单个元素。
当只需要正向遍历时列表优先于列表(与单链表优先于双链表相同)，因为我们可以节省空间。一些例子是，散列中的链接，图的邻接表表示等。

**与转发列表一起使用的功能:**

*   **push _ front(x):**–在列表的开头添加一个新元素‘x’。

**<u>向量</u>**

[**<u>【向量】</u>**](https://www.geeksforgeeks.org/vector-in-cpp-stl/) 与动态数组相同，能够在插入或删除元素时自动调整自身大小，其存储由容器自动处理。

**与向量一起使用的函数:**

*   **size():** 返回向量中元素的个数。
*   **push_back():** 此功能用于将元素从后面推入矢量。

在设计复杂的数据结构时，向量列表非常有用。每个节点可以保存一个向量。

下面是矢量列表的实现:

## C++

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to print list
// contents
void print(list<vector<int> >& listOfVectors)
{
    for (auto vect : listOfVectors) {
        // Each element of the list is
        // a vector itself
        vector<int> currentVector = vect;

        cout << "[ ";

        // Printing vector contents
        for (auto element : currentVector)
            cout << element << ' ';

        cout << ']';
        cout << '\n';
    }
}

// Driver code
int main()
{
    // Declaring a list of vectors
    list<vector<int> > listOfVectors;

    // Declaring a vector
    vector<int> vector1;

    // Adding elements into the
    // vector
    vector1.push_back(10);
    vector1.push_back(14);
    vector1.push_back(17);

    // Push the vector at the back
    // in the list
    listOfVectors.push_back(vector1);

    // Declaring another vector
    vector<int> vector2;

    // Adding elements in the vector
    vector2.push_back(2);
    vector2.push_back(6);
    vector2.push_back(11);

    // Push the vector at the back
    // in the list
    listOfVectors.push_back(vector2);

    // Declaring another vector
    vector<int> vector3;

    // Adding elements in the
    // vector
    vector3.push_back(11);
    vector3.push_back(16);
    vector3.push_back(29);

    // Push the vector at the front
    // in the list
    listOfVectors.push_front(vector3);

    // Calling print function
    print(listOfVectors);
    return 0;
}
```

**Output**

```cpp
[ 10 14 17 ]
[ 2 6 11 ]
[ 11 16 29 ]
```

下面是矢量正向列表的实现:

## C++

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to print forward
// list contents
void print(forward_list<vector<int> >& forwardListOfVectors)
{
    for (auto vect : forwardListOfVectors) {
        // Each element of the forward list
        // is a vector itself
        vector<int> currentVector = vect;

        cout << "[ ";

        // Printing vector contents
        for (auto element : currentVector)
            cout << element << ' ';

        cout << ']';
        cout << '\n';
    }
}

// Driver code
int main()
{
    // Declaring a list of vectors
    forward_list<vector<int> > forwardListOfVectors;

    // Declaring a vector
    vector<int> vector1;

    // Adding elements into the vector
    vector1.push_back(10);
    vector1.push_back(14);
    vector1.push_back(17);

    // Push the vector in the forward
    // list
    forwardListOfVectors.push_front(vector1);

    // Declaring another vector
    vector<int> vector2;

    // Adding elements in the vector
    vector2.push_back(2);
    vector2.push_back(6);
    vector2.push_back(11);

    // Push the vector in the forward
    // list
    forwardListOfVectors.push_front(vector2);

    // Declaring another vector
    vector<int> vector3;

    // Adding elements in the vector
    vector3.push_back(11);
    vector3.push_back(16);
    vector3.push_back(29);

    // Push the vector in the forward
    // list
    forwardListOfVectors.push_front(vector3);

    // Calling print function
    print(forwardListOfVectors);

    return 0;
}
```

**Output**

```cpp
[ 11 16 29 ]
[ 2 6 11 ]
[ 10 14 17 ]
```