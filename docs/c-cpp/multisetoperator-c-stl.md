# 多集::运算符=在 C++ STL 中

> 原文:[https://www.geeksforgeeks.org/multisetoperator-c-stl/](https://www.geeksforgeeks.org/multisetoperator-c-stl/)

[多集合](https://www.geeksforgeeks.org/multiset-in-cpp-stl/)是一种类似于集合的关联容器，不同的是多个元素可以有相同的值。

**multiset::operator=**

该运算符用于通过替换现有内容向容器分配新内容。
还会根据新内容修改大小。

**语法:**

```cpp
*multisetname1* = (*multisetname2*)
Parameters :
Another container of the same type.
Result :
Assign the contents of the container passed as 
parameter to the container written on left side of the operator.

```

**set::operator=**

该运算符用于通过替换现有内容向容器分配新内容。
还会根据新内容修改大小。

**语法:**

```cpp
*setname1* = (*setname2*)
Parameters :
Another container of the same type.
Result :
Assign the contents of the container passed as 
parameter to the container written on left side of the operator.

```

示例:

```cpp
Input  :  mymultiset1 = 1, 2, 3
          mymultiset2 = 3, 2, 1, 4
          mymultiset1 = mymultiset2;
Output :  mymultiset1 = 3, 2, 1, 4

Input  :  mymultiset1 = 2, 6, 1, 5
          mymultiset2 = 3, 2
          mymultiset1 = mymultiset2;
Output :  mymultiset1 = 3, 2

```

```cpp
Input  :  myset1 = 1, 2, 3
          myset2 = 3, 2, 1, 4
          myset1 = myset2;
Output :  myset1 = 3, 2, 1, 4

Input  :  myset1 = 2, 6, 1, 5
          myset2 = 3, 2
          myset1 = myset2;
Output :  myset1 = 3, 2

```

**错误和异常**

1.如果容器的类型不同，则会引发错误。
2。否则它有一个基本的无异常抛出保证。

```cpp
// INTEGER MULISET EXAMPLE
// CPP program to illustrate
// Implementation of = operator
#include <iostream>
#include <set>
using namespace std;

int main()
{
    multiset<int> mymultiset1{ 1, 7, 4, 9, 0};
    multiset<int> mymultiset2{ 3, 4 };
    mymultiset1 = mymultiset2;
    cout << "mymultiset1 = ";
    for (auto it = mymultiset1.begin();
              it != mymultiset1.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
mymultilist1 = 3 4

```

```cpp
// CHARACTER MULTISET EXAMPLE
// CPP program to illustrate
// Implementation of = operator
#include <iostream>
#include <set>
using namespace std;

int main()
{
    multiset<char> mymultiset1{ 'a', 'b', 'c'};
    multiset<char> mymultiset2{ 'x', 'y' };
    mymultiset1 = mymultiset2;
    cout << "mymultiset1 = ";
    for (auto it = mymultiset1.begin();
              it != mymultiset1.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
mymultilist1 = x y

```

```cpp
// STRING MULTISET EXAMPLE
// CPP program to illustrate
// Implementation of = operator
#include <iostream>
#include <set>
#include<string>
using namespace std;

int main()
{
    multiset<string> mymultiset1{ "This","is","a","computer science portal"};
    multiset<string> mymultiset2{ "GeeksForGeeks" };
    mymultiset1 = mymultiset2;
    cout << "mymultiset1 = ";
    for (auto it = mymultiset1.begin();
              it != mymultiset1.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
mymultilist1 = GeeksForGeeks

```

**时间复杂度:** O(n)

```cpp
// CPP program to illustrate
// Implementation of = operator
#include <iostream>
#include <set>
#include<string>
using namespace std;

int main()
{
    set<string> myset1{ "This","is","a","computer science portal"};
    set<string> myset2{ "GeeksForGeeks" };
    myset1 = myset2;
    cout << "myset1 = ";
    for (auto it = myset1.begin();
              it != myset1.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
mylist1 = GeeksForGeeks

```

**时间复杂度:** O(n)