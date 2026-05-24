# c++ STL 中的嵌套列表

> 原文:[https://www.geeksforgeeks.org/nested-list-in-c-stl/](https://www.geeksforgeeks.org/nested-list-in-c-stl/)

STL 中的[列表](https://www.geeksforgeeks.org/list-cpp-stl/)用于表示 C++ 中的链表。如何创建嵌套列表？给我们 n 个列表，我们需要创建 n 个列表的列表。

示例:

```cpp
Input :  Number of lists: 2
1st list: {1 2}
2nd list:  {3 4 5 6
Output : 
[
  [ 1  2 ]
  [ 3  4  5  6 ]
]

Input : Number of lists: 3
1st list : {0 1} 
2nd list : {1 2 3}
3rd list : {2 3 4 5}
Output :
[
  [ 0  1 ]
  [ 1  2  3 ]
  [ 2  3  4  5 ]
]

```

```cpp
// c++ program for nested list

#include <iostream>
#include <iterator>
#include <list>
using namespace std;

void printNestedList(list<list<int> > nested_list)
{
    cout << "[\n";

    // nested_list`s iterator(same type as nested_list)
    // to iterate the nested_list
    list<list<int> >::iterator nested_list_itr;

    // Print the nested_list
    for (nested_list_itr = nested_list.begin();
         nested_list_itr != nested_list.end();
         ++ nested_list_itr) {

        cout << "  [";

        // normal_list`s iterator(same type as temp_list)
        // to iterate the normal_list
        list<int>::iterator single_list_itr;

        // pointer of each list one by one in nested list
        // as loop goes on
        list<int>& single_list_pointer = *nested_list_itr;

        for (single_list_itr = single_list_pointer.begin();
             single_list_itr != single_list_pointer.end();
             single_list_itr++) {
            cout << " " << *single_list_itr << " ";
        }
        cout << "]\n";
    }
    cout << "]";
}

// Driver code
int main()
{
    // instead integer type can have any data type
    list<list<int> > nested_list;
    list<int> single_list;
    int n, m, num;

    // number of lists in nested list
    n = 3;

    for (int i = 0; i < n; i++) {

        // number of elements in list
        m = i + 2;
        for (int j = 0; j < m; j++) {
            num = i + j;
            single_list.push_back(num);
        }

        nested_list.push_back(single_list);

        // delete all elements from single_list
        single_list.erase(single_list.begin(),
                          single_list.end());
    }

    printNestedList(nested_list);

    return 0;
}
```

**Output:**

```cpp
[
  [ 0  1 ]
  [ 1  2  3 ]
  [ 2  3  4  5 ]
]

```