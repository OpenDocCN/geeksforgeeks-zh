# c++ 中列表和转发列表的集合，示例

> 原文:[https://www . geeksforgeeks . org/list-of-list-on-forward-list-in-c-with-examples/](https://www.geeksforgeeks.org/set-of-list-and-forward-list-in-c-with-examples/)

**<u>套</u>**

[](https://www.geeksforgeeks.org/set-in-cpp-stl/)<u>集合是一种关联容器，其中每个元素必须是唯一的，因为元素的值标识了它。元素的值一旦被添加到集合中就不能被修改，尽管可以移除和添加该元素的修改值。</u>

<u>与集合一起使用的函数:</u>

*   <u>[**<u>begin ():</u>**](https://www.geeksforgeeks.org/setbegin-setend-c-stl/) An iterator that returns the first element in the set.</u>
*   <u>[**<u>end ()</u>**](https://www.geeksforgeeks.org/setbegin-setend-c-stl/) **:** An iterator that returns the theoretical elements after the last element in the set.</u>
<u>*   [**<u>Size ()</u>**](https://www.geeksforgeeks.org/setsize-c-stl/) **:** Returns the number of elements in a set.*   [**<u>Max _ size ()</u>**](https://www.geeksforgeeks.org/set-max_size-function-in-c-stl/) **:** Returns the maximum prime number that a set can hold.*   [**<u>Empty ()</u>**](https://www.geeksforgeeks.org/setempty-c-stl/) **: Returns whether the set is empty or not.**</u>

<u>**<u>列出</u>**</u>

<u>[<u>列表</u>](https://www.geeksforgeeks.org/list-cpp-stl/) 是允许非连续内存分配的序列容器。与 vector 相比，列表遍历速度慢，但是一旦找到位置，插入和删除就很快。通常，当我们说一个列表时，我们说的是一个双链表。为了实现单链表，我们使用和转发列表。</u>

<u>与 list 一起使用的函数:</u>

*   <u>**Push _ front ():** This function is used to push elements into the list from the front.</u>
<u>*   **Push _ back ():** This function is used to push elements into the list from behind.</u>

<u>**<u>转发列表</u>**</u>

<u>[<u>STL 中的正向列表</u>](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/) 实现单链表。前向列表是从 C++ 11 引入的，在插入、移除和移动操作(如排序)方面比其他容器更有用，并且允许元素的时间常数插入和移除。</u>

<u>与前进列表一起使用的函数:</u>

<u>*   **Push _ front ():** This function is used to push elements into the forward list from the front.</u>

<u>**<u>STL 中的器械包列表</u>**</u>

<u>一组列表在设计复杂的数据结构时非常有用。</u>

<u>**语法:**</u>

```cpp
**set<list<data_type>> set_of_list:** This stores lists. 
**set<forward_list<data_type>> set_of_forward_list:** This stores forward lists.
```

<u>下面是 C++ 程序演示实现的一组列表:</u>

## <u>c++ </u>

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to print set contents
void print(set<list<int> >& setOfList)
{
    for (auto x : setOfList) {
        // Each element of the set is
        // a list itself
        list<int> li = x;

        // Printing list elements
        cout << "[ ";
        for (auto element : li)
            cout << element << ' ';
        cout << ']';
        cout << '\n';
    }
}

// Driver code
int main()
{
    set<list<int> > setOfList;

    // Declaring a list
    list<int> list1;

    // Pushing elements in the list
    // Pushing at the back
    list1.push_back(10);
    list1.push_back(12);

    // Pushing at the front
    list1.push_front(21);

    // Pushing at the back
    list1.push_back(16);

    // Inserting a list into the set
    setOfList.insert(list1);

    // Declaring another list
    list<int> list2;

    // Pushing elements in the list
    // Pushing at the back
    list2.push_back(6);
    list2.push_back(9);
    list2.push_back(11);

    // Pushing at the front
    list2.push_front(2);

    setOfList.insert(list2);

    // Declaring another list
    list<int> list3;

    // Pushing elements in the list
    // Pushing at the back
    list3.push_back(2);
    list3.push_back(6);
    list3.push_back(9);
    list3.push_back(1);

    setOfList.insert(list3);

    print(setOfList);

    return 0;
}
```

<u>**输出**

```cpp
[ 2 6 9 1 ]
[ 2 6 9 11 ]
[ 21 10 12 16 ]
```</u> 

<u>下面是 C++ 程序演示一组转发列表的实现:</u>

<u>T3】c++ T5

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to print set contents
void print(set<forward_list<int> >& setOfForwardList)
{
    for (auto x : setOfForwardList) {
        // Each element is a forward list
        // itself
        forward_list<int> li = x;
        cout << "[ ";

        for (auto element : li)
            cout << element << ' ';

        cout << ']';
        cout << '\n';
    }
}

// Driver code
int main()
{
    // Declaring a setOfForwardList
    set<forward_list<int> > setOfForwardList;

    // Declaring a forward list
    forward_list<int> forwardList1;

    // Pushing elements in the forward
    // list
    forwardList1.push_front(10);
    forwardList1.push_front(12);
    forwardList1.push_front(21);
    forwardList1.push_front(16);

    // Inserting forward list into
    // the set
    setOfForwardList.insert(forwardList1);

    // Declaring another forward list
    forward_list<int> forwardList2;

    // Pushing elements in the forward
    // list
    forwardList2.push_front(6);
    forwardList2.push_front(9);
    forwardList2.push_front(11);
    forwardList2.push_front(2);

    // Inserting forward list into
    // the set
    setOfForwardList.insert(forwardList2);

    // Print set contents
    print(setOfForwardList);

    return 0;
}
```

T6</u><u>T8**输出**T1

默认情况下，列表在集合中以非降序排列，并遵循集合中的逻辑，如果两个列表的第一个值相等，则比较列表的第二个值，依此类推。</u>