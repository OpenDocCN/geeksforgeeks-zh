# c++ STL 中的 list::remove()和 list::remove _ if()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/listremove-listremove _ if-c-STL/

[列表](https://www.geeksforgeeks.org/list-cpp-stl/)是 C++ 中用于以非连续方式存储数据的容器，通常，数组和向量本质上是连续的，因此与列表中的插入和删除选项相比，插入和删除操作的成本更高。

**list::remove()**

remove()函数用于从列表中删除与作为函数参数给出的值相对应的所有值
**语法:**

```cpp
***listname.remove(value)***
Parameters :
The value of the element to be removed is passed as the parameter.
Result :
Removes all the elements of the container
equal to the value passed as parameter
```

示例:

```cpp
Input  : list list{1, 2, 3, 4, 5};
         list.remove(4);
Output : 1, 2, 3, 5

Input  : list list{1, 2, 2, 2, 5, 6, 7};
         list.remove(2);
Output : 1, 5, 6, 7
```

**错误和异常**

1.  如果传递的值与列表类型不匹配，则显示错误。
2.  如果列表功能的值和元素之间的比较没有引发任何异常，则不显示异常引发保证。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of remove() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    list<int> mylist{ 1, 2, 2, 2, 5, 6, 7 };
    mylist.remove(2);
    for (auto it = mylist.begin(); it != mylist.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
1 5 6 7
```

**list::remove_if()**

remove_if()函数用于从列表中删除与作为函数参数给出的*谓词*或条件相对应的所有值。该函数遍历列表容器的每个成员，并移除所有为谓词返回 true 的元素。
**语法:**

```cpp
***listname.remove_if(predicate)***
Parameters :
The predicate in the form of aa function pointer
or function object is passed as the parameter.
Result :
Removes all the elements of the container
which return true for the predicate.
```

示例:

```cpp
Input  : list list{1, 2, 3, 4, 5};
         list.remove_if(odd);
Output : 2, 4

Input  : list list{1, 2, 2, 2, 5, 6, 7};
         list.remove_if(even);
Output : 1, 5, 7
```

**错误和异常**

1.  如果谓词函数特性不抛出任何异常，则不显示异常抛出保证。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of remove_if() function
#include <iostream>
#include <list>
using namespace std;

// Predicate implemented as a function
bool even(const int& value) { return (value % 2) == 0; }

// Main function
int main()
{
    list<int> mylist{ 1, 2, 2, 2, 5, 6, 7 };
    mylist.remove_if(even);
    for (auto it = mylist.begin(); it != mylist.end(); ++ it)
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

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Application of remove_if() function
#include <iostream>
#include <list>
using namespace std;

// Predicate implemented as a function
bool prime(const int& value)
{
    int i;
    for (i = 2; i < value; i++) {
        if (value % i == 0) {
            return false;

        }
    }
    if (value == i) {
        return true;
    }
}

// Main function
int main()
{
    list<int> mylist{ 2, 4, 6, 7, 9, 11, 13 };
    mylist.remove_if(prime);
    for (auto it = mylist.begin(); it != mylist.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
4 6 9
```