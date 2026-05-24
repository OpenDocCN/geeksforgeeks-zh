# c++ STL 中列表和 forward_list 的映射及示例

> 原文:[https://www . geesforgeks . org/list-of-list-and-forward _ list-in-c-STL-with-examples/](https://www.geeksforgeeks.org/map-of-list-and-forward_list-in-c-stl-with-examples/)

[](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)<u>是以映射方式存储元素的关联容器。每个元素都有一个键值和一个映射值。没有两个映射值可以具有相同的键值。</u>

<u>[<u>列表</u>](https://www.geeksforgeeks.org/list-cpp-stl/) 是允许非连续内存分配的序列容器。与 vector 相比，列表遍历速度慢，但是一旦找到位置，插入和删除就很快。列表仅仅意味着双向链表，对于单向链表，使用正向链表。</u>

<u>**<u>STL 列表地图</u>**</u>

<u>列表图在设计复杂的数据结构时非常有用。</u>

<u>**语法:**</u>

```cpp
**map<datatype, list<datatype>> map_of_list** 
This stores a list corresponding to a datatype

or

**map<list<datatype>, datatype> map_of_list**
This stores a datatype corresponding to a list
```

<u>下面是列表地图在 c++-</u>

## <u>c++ </u>

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

void printMapContent1(map<list<int>,
                          int>& mapOfList)
{
    cout << "   Key         Value"
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

        cout << "     ";

        // Printing value
        cout << mapOfList[ourList] << '\n';
    }
}

void printMapContent2(map<int,
                          list<int> >& mapOfList)
{

    cout << "   Key         Value"
         << "\n\n";
    for (auto p : mapOfList) {
        // Key is an integer
        int key = p.first;

        // Value is a list of integers
        list<int> ourList = p.second;

        cout << "   ";
        cout << key << "          ";

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

<u>**中的实现输出**

```cpp
   Key         Value

[ 2 10 13 ]     5
[ 7 14 22 ]     10

   Key         Value

   3          [ 2 10 13 ]
   7          [ 7 14 22 ]
```</u> 

<u>**<u>STL 中的转发列表</u>**</u>

<u>STL 中的正向列表实现单链表。从 C++ 11 引入，forward 列表在插入、移除、和移动操作(如排序)方面比其他容器更有用，并且允许时间常数插入和移除元素。 forward_list 也可以和地图容器一起使用。</u>

<u>**语法:**</u>

```cpp
**map<datatype, forward_list<datatype>> map_of_list**
This stores a forward list corresponding to a datatype

or

**map<forward_list<datatype>, datatype> map_of_list**
This stores a datatype corresponding to a forward list
```

<u>下面是 C++ 中 forward_list 的实现-</u>

<u>T3】c++ T5

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

void printMapContent1(map<forward_list<int>,
                          int>& mapOfList)
{
    cout << "   Key         Value"
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
        cout << "     ";

        // Printing value
        cout << mapOfList[ourList] << '\n';
    }
}

void printMapContent2(map<int,
                          forward_list<int> >& mapOfList)
{

    cout << "   Key         Value"
         << "\n\n";
    for (auto p : mapOfList) {
        // Key is an integer
        int key = p.first;

        // Value is a list of integers
        forward_list<int> ourList = p.second;

        cout << "   ";
        cout << key << "          ";

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

T6</u><u>T8**输出**T1</u>