# c++ STL 中的 forward_list::remove()和 forward _ list::remove _ if()

> 原文:[https://www . geesforgeks . org/forward _ list remove-forward _ list remove _ if-c-STL/](https://www.geeksforgeeks.org/forward_listremove-forward_listremove_if-c-stl/)

[STL 中的正向列表](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/)实现单链表。前向列表是从 C++ 11 引入的，在插入、移除和移动操作(如排序)方面比其他容器更有用，并且允许元素的时间常数插入和移除。它不同于列表，因为转发列表只跟踪下一个元素的位置，而列表跟踪下一个和上一个元素。

**forward_list::remove()**

remove()函数用于从转发列表中删除与作为函数参数给出的值相对应的所有值

**语法:**

```cpp
*forwardlistname*.remove(*value*)
Parameters :
The value of the element to be removed is passed as the parameter.
passed as the parameter
Result :
Removes all the elements of the container
equal to the value passed as parameter

```

示例:

```cpp
Input : forward_list forwardlist{1, 2, 3, 4, 5};
        forwardlist.remove(4);
Output :1, 2, 3, 5

Input : forward_list forwardlist{1, 2, 2, 2, 5, 6};
        forwardlist.remove(2);
Output :1, 5, 6

```

**错误和异常**

1.如果传递的值与转发列表类型不匹配，则显示错误。
2。如果正向列表功能的值和元素之间的比较没有引发任何异常，则不显示异常引发保证。

```cpp
// CPP program to illustrate
// Implementation of remove() function
#include <forward_list>
#include <iostream>
using namespace std;

int main()
{
    forward_list<int> myforwardlist{ 1, 2, 2, 2, 5, 6, 7 };
    myforwardlist.remove(2);
    for (auto it = myforwardlist.begin(); it != myforwardlist.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
1 5 6 7

```

**forward_list::remove_if()**

remove_if()函数用于从列表中移除所有值，这些值对应于作为函数参数给出的谓词或条件。该函数遍历列表容器的每个成员，并移除所有为谓词返回 true 的元素。

**语法:**

```cpp
*forwardlistname*.remove_if(*predicate*)
Parameters :
The predicate in the form of a function pointer
or function object is passed as the parameter.
Result :
Removes all the elements of the container
which return true for the predicate.

```

示例:

```cpp
Input  : forward_list forwardlist{1, 2, 3, 4, 5};
         forwardlist.remove_if(odd);
Output : 2, 4

Input  : forward_list forwardlist{1, 2, 2, 2, 5, 6, 7};
         forwardlist.remove_if(even);
Output : 1, 5, 7

```

**错误和异常**

1.如果谓词函数特性不抛出任何异常，则不显示异常抛出保证。

```cpp
// CPP program to illustrate
// Implementation of remove_if() function
#include <forward_list>
#include <iostream>
using namespace std;

// Predicate implemented as a function
bool even(const int& value) { return (value % 2) == 0; }

// Main function
int main()
{
    forward_list<int> myforwardlist{ 1, 2, 2, 2, 5, 6, 7 };
    myforwardlist.remove_if(even);
    for (auto it = myforwardlist.begin(); it != myforwardlist.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
1 5 7

```

**应用:**给定一个整数列表，从列表中去掉所有质数，打印列表。

```cpp
Input  : 2, 4, 6, 7, 9, 11, 13
Output : 4, 6, 9

```

```cpp
// CPP program to illustrate
// Application of remove_if() function
#include <forward_list>
#include <iostream>
using namespace std;

// Predicate implemented as a function
bool prime(const int& value)
{
    int i;
    for (i = 2; i < value; i++) {
        if (value % i == 0) {
            return false;
            ;
            break;
        }
    }
    if (value == i) {
        return true;
        ;
    }
}

// Main function
int main()
{
    forward_list<int> myforwardlist{ 2, 4, 6, 7, 9, 11, 13 };
    myforwardlist.remove_if(prime);
    for (auto it = myforwardlist.begin(); it != myforwardlist.end(); ++ it)
        cout << ' ' << *it;
}
```

输出

```cpp
4 6 9

```