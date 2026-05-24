# c++ STL 中的 list::empty()和 list::size()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/listmpty-listsize-c-STL/

[列表](https://www.geeksforgeeks.org/list-cpp-stl/)是 C++ 中用来以非连续方式存储数据的容器。通常，数组和向量本质上是连续的，因此与列表中的插入和删除选项相比，插入和删除操作的成本更高。

**list::empty()**

empty()函数用于检查列表容器是否为空。

**语法:**

```cpp
*listname*.empty()
Parameters :
No parameters are passed.
Returns :
True, if list is empty
False, Otherwise

```

示例:

```cpp
Input  : list list{1, 2, 3, 4, 5};
         list.empty();
Output : False

Input  : list list{};
         list.empty();
Output : True

```

**错误和异常**

1.  它有一个无异常抛出保证。
2.  传递参数时显示错误。

```cpp
// CPP program to illustrate
// Implementation of empty() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    list<int> mylist{};
    if (mylist.empty()) {
        cout << "True";
    }
    else {
        cout << "False";
    }
    return 0;
}
```

输出:

```cpp
True

```

**应用:**
给定一个整数列表，求所有整数的和。

```cpp
Input  : 1, 5, 6, 3, 9, 2
Output : 26
*Explanation - * 1+5+6+3+9+2 = 26

```

**算法**

1.  检查列表是否为空，如果不是，将前端元素添加到初始化为 0 的变量中，并弹出前端元素。
2.  重复此步骤，直到列表为空。
3.  打印变量的最终值。

```cpp
// CPP program to illustrate
// Application of empty() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    int sum = 0;
    list<int> mylist{ 1, 5, 6, 3, 9, 2 };
    while (!mylist.empty()) {
        sum = sum + mylist.front();
        mylist.pop_front();
    }
    cout << sum;
    return 0;
}
```

输出:

```cpp
26

```

**list::size()**

size()函数用于返回列表容器的大小或列表容器中的元素数量。

**语法:**

```cpp
*listname*.size()
Parameters :
No parameters are passed.
Returns :
Number of elements in the container.

```

示例:

```cpp
Input  : list list{1, 2, 3, 4, 5};
         list.size();
Output : 5

Input  : list list{};
         list.size();
Output : 0

```

**错误和异常**

1.  它有一个无异常抛出保证。
2.  传递参数时显示错误。

```cpp
// CPP program to illustrate
// Implementation of size() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    list<int> mylist{ 1, 2, 3, 4, 5 };
    cout << mylist.size();
    return 0;
}
```

输出:

```cpp
5

```

**应用:**
给定一个整数列表，求所有整数的和。

```cpp
Input  : 1, 5, 6, 3, 9, 2
Output : 26
*Explanation - * 1+5+6+3+9+2 = 26

```

**算法**

1.  检查列表的大小是否为 0，如果不是，将前端元素添加到初始化为 0 的变量中，并弹出前端元素。
2.  重复此步骤，直到列表为空。
3.  打印变量的最终值。

```cpp
// CPP program to illustrate
// Application of size() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    int sum = 0;
    list<int> mylist{ 1, 5, 6, 3, 9, 2 };
    while (mylist.size() > 0) {
        sum = sum + mylist.front();
        mylist.pop_front();
    }
    cout << sum;
    return 0;
}
```

输出:

```cpp
26

```