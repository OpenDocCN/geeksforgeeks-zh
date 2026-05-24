# c++ STL 中的 forward_list::炮位 _front()

> 原文:[https://www . geeksforgeeks . org/forward _ listitle _ front-in-cstl/](https://www.geeksforgeeks.org/forward_listemplace_front-in-cstl/)

[STL 中的正向列表](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/)实现单链表。前向列表是从 C++ 11 引入的，它比其他容器在插入、移除和移动操作(如排序)方面更有用，并且允许元素的时间常数插入和移除。它与列表的不同之处在于转发列表只跟踪下一个元素的位置，而列表同时跟踪下一个和上一个元素。

**forward_list::emplace_front()**

该函数用于将新的元素插入到转发列表容器中，新的元素被添加到转发列表的开头。
**语法:**

```cpp
*forwardlistname*.emplace_front(*value*)
Parameters :
The element to be inserted into the forward list
is passed as the parameter.
Result :
The parameter is added to the
forward list at the beginning.

```

示例:

```cpp
Input  : myflist{1, 2, 3, 4, 5};
         myflist.emplace_front(6);
Output : myflist = 6, 1, 2, 3, 4, 5

Input  : myflist{};
         myflist.emplace_front(4);
Output : myflist = 4

```

**错误和异常**
1。它有很强的异常保证，因此，如果抛出异常，不会进行任何更改。
2。参数应该与容器的类型相同，否则会引发错误。

```cpp
// INTEGER FORWARD LIST EXAMPLE
// CPP program to illustrate
// Implementation of emplace() function
#include <forward_list>
#include <iostream>
using namespace std;

int main() {
  forward_list<int> myflist;
  myflist.emplace_front(1);
  myflist.emplace_front(2);
  myflist.emplace_front(3);
  myflist.emplace_front(4);
  myflist.emplace_front(5);
  myflist.emplace_front(6);
  // forward list becomes 6, 5, 4, 3, 2, 1

  // printing the forward list
  for (auto it = myflist.begin(); it != myflist.end(); ++ it)
    cout << ' ' << *it;

  return 0;
}
```

输出:

```cpp
6 5 4 3 2 1

```

```cpp
// STRING FORWARD LIST EXAMPLE
// CPP program to illustrate
// Implementation of emplace() function
#include <forward_list>
#include <iostream>
#include <string>
using namespace std;

int main() {
  forward_list<string> myflist;
  myflist.emplace_front("Geeksforgeeks");
  myflist.emplace_front("is");
  myflist.emplace_front("This");
  // forward list becomes This, is, Geeksforgeeks

  // printing the forward list
  for (auto it = myflist.begin(); it != myflist.end(); ++ it)
    cout << ' ' << *it;

  return 0;
}
```

输出:

```cpp
This is Geeksforgeeks

```

```cpp
// CHARACTER FORWARD LIST EXAMPLE
// CPP program to illustrate
// Implementation of emplace() function
#include <forward_list>
#include <iostream>
using namespace std;

int main() {
  forward_list<char> myflist;
  myflist.emplace_front('z');
  myflist.emplace_front('y');
  myflist.emplace_front('x');
  myflist.emplace_front('b');
  myflist.emplace_front('a');
  // forward list becomes a, b, x, y, z

  // printing the forward list
  for (auto it = myflist.begin(); it != myflist.end(); ++ it)
    cout << ' ' << *it;

  return 0;
}
```

输出:

```cpp
a b x y z

```

**时间复杂度:** O(1)

**应用:**使用侵位 _front()函数输入一个空的前向列表，并对给定的前向列表进行排序。

```cpp
Input :  7, 89, 45, 6, 24, 58, 43
Output : 6, 7, 24, 43, 45, 58, 89
```

```cpp
// CPP program to illustrate
// application Of emplace_front() function
#include <forward_list>
#include <iostream>
using namespace std;

int main() {
  forward_list<int> myforwardlist{};
  myforwardlist.emplace_front(43);
  myforwardlist.emplace_front(58);
  myforwardlist.emplace_front(24);
  myforwardlist.emplace_front(6);
  myforwardlist.emplace_front(45);
  myforwardlist.emplace_front(89);
  myforwardlist.emplace_front(7);

  // Forward list becomes
  // 7, 89, 45, 6, 24, 58, 43

  // Sorting function
  myforwardlist.sort();

  for (auto it = myforwardlist.begin(); it != myforwardlist.end(); ++ it)
    cout << ' ' << *it;
}
```

输出

```cpp
6 7 24 43 45 58 89

```