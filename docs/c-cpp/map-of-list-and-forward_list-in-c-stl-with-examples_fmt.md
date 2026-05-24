# C++ STL 中 list 和 forward_list 的映射及示例

> 原文：[https://www.geeksforgeeks.org/map-of-list-and-forward_list-in-c-stl-with-examples/](https://www.geeksforgeeks.org/map-of-list-and-forward_list-in-c-stl-with-examples/)

[`map`](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/) 是以映射方式存储元素的关联容器。每个元素都有一个键值和一个映射值。没有两个映射值可以具有相同的键值。

[`list`](https://www.geeksforgeeks.org/list-cpp-stl/) 是允许非连续内存分配的序列容器。与 `vector` 相比，`list` 遍历速度慢，但是一旦找到位置，插入和删除就很快。`list` 仅仅意味着双向链表，对于单向链表，使用 `forward_list`。

## STL list map

`list` map 在设计复杂的数据结构时非常有用。

### 语法

```cpp
map<datatype, list<datatype>> map_of_list
// This stores a list corresponding to a datatype

// or

map<list<datatype>, datatype> map_of_list
// This stores a datatype corresponding to a list
```

下面是 `list` map 在 C++ 中的实现：

### C++ 示例

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

void printMapContent1(map<list<int>,
                              int>& mapOfList)
{
    cout << "   Key         Value"
         << "\n\n";
    for (auto p : mapOfList) {
        // Key is a list of integers
        list<int> ourList = p.first;

        // Value is an integer
        int val = p.second;

        // Printing list elements
        cout << "[ ";
        for (auto it = ourList.begin();
             it != ourList.end(); it++) {
            // Deferencing value pointed by
            // iterator
            cout << (*it) << ' ';
        }

        cout << ']';

        cout << "     ";

        // Printing value
        cout << mapOfList[ourList] << '\n';
    }
}

void printMapContent2(map<int,
                              list<int> >& mapOfList)
{

    cout << "   Key         Value"
         << "\n\n";
    for (auto p : mapOfList) {
        // Key is an integer
        int key = p.first;

        // Value is a list of integers
        list<int> ourList = p.second;

        cout << "   ";
        cout << key << "          ";

        // Printing list elements
        cout << "[ ";
        for (auto it = ourList.begin();
             it != ourList.end(); it++) {
            // Deferencing value pointed by
            // iterator
            cout << (*it) << ' ';
        }

        cout << ']';
        cout << '\n';
    }
}

// Driver code
int main()
{
    // Declaring a list of integers
    list<int> ourList1;

    // Inserting elements at the
    // back of list
    ourList1.push_back(2);
    ourList1.push_back(10);
    ourList1.push_back(13);

    // Declaring another list
    list<int> ourList2;

    // Inserting elements at the back
    // of list
    ourList2.push_back(7);
    ourList2.push_back(14);
    ourList2.push_back(22);

    // Declaring a map where key is a list
    // and value is integer itself
    map<list<int>, int> mapOfList1;

    mapOfList1[ourList1] = 5;
    mapOfList1[ourList2] = 10;

    // Printing the contents of the map
    printMapContent1(mapOfList1);

    // Declaring a map where key is integer
    // and value is a list of integers
    map<int, list<int> > mapOfList2;

    cout << "\n\n";
    mapOfList2[3] = ourList1;
    mapOfList2[7] = ourList2;

    printMapContent2(mapOfList2);

    return 0;
}
```

### 输出

```cpp
   Key         Value

[ 2 10 13 ]     5
[ 7 14 22 ]     10

   Key         Value

   3          [ 2 10 13 ]
   7          [ 7 14 22 ]
```

## STL 中的 forward_list

STL 中的 `forward_list` 实现单链表。从 C++ 11 引入，`forward_list` 在插入、移除、和移动操作(如排序)方面比其他容器更有用，并且允许时间常数插入和移除元素。`forward_list` 也可以和 `map` 容器一起使用。

### 语法

```cpp
map<datatype, forward_list<datatype>> map_of_list
// This stores a forward list corresponding to a datatype

// or

map<forward_list<datatype>, datatype> map_of_list
// This stores a datatype corresponding to a forward list
```

下面是 C++ 中 `forward_list` 的实现：

### C++ 示例

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

void printMapContent1(map<forward_list<int>,
                              int>& mapOfList)
{
    cout << "   Key         Value"
         << "\n\n";
    for (auto p : mapOfList) {
        // Key is a list of integers
        forward_list<int> ourList = p.first;

        // Value is an integer
        int val = p.second;

        // Printing list elements
        cout << "[ ";
        for (auto it = ourList.begin();
             it != ourList.end(); it++) {
            // Deferencing value pointed by
            // iterator
            cout << (*it) << ' ';
        }

        cout << ']';
        cout << "     ";

        // Printing value
        cout << mapOfList[ourList] << '\n';
    }
}

void printMapContent2(map<int,
                              forward_list<int> >& mapOfList)
{

    cout << "   Key         Value"
         << "\n\n";
    for (auto p : mapOfList) {
        // Key is an integer
        int key = p.first;

        // Value is a list of integers
        forward_list<int> ourList = p.second;

        cout << "   ";
        cout << key << "          ";

        // Printing list elements
        cout << "[ ";
        for (auto it = ourList.begin();
             it != ourList.end(); it++) {
            // Deferencing value pointed by
            // iterator
            cout << (*it) << ' ';
        }

        cout << ']';
        cout << "\n";
    }
}

// Driver code
int main()
{
    // Declaring forward list
    forward_list<int> forwardList1;

    // Declaring another forward list
    forward_list<int> forwardList2;

    // Assigning values using assign()
    forwardList1.assign({ 5, 3, 13 });
    forwardList2.assign({ 8, 9, 13 });

    map<forward_list<int>,
        int>
        mapOfList1;

    mapOfList1[forwardList1] = 3;
    mapOfList1[forwardList2] = 7;

    printMapContent1(mapOfList1);
    cout << "\n\n";

    map<int,
        forward_list<int> >
        mapOfList2;

    mapOfList2[3] = forwardList1;
    mapOfList2[7] = forwardList2;

    printMapContent2(mapOfList2);
    return 0;
}
```

### 输出

```cpp
   Key         Value

[ 5 3 13 ]     3
[ 8 9 13 ]     7

   Key         Value

   3          [ 5 3 13 ]
   7          [ 8 9 13 ]
```