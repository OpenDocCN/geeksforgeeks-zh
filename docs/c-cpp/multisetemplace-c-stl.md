# c++ STL 中的多集::侵位()

> 原文:[https://www.geeksforgeeks.org/multisetemplace-c-stl/](https://www.geeksforgeeks.org/multisetemplace-c-stl/)

[多集合](https://www.geeksforgeeks.org/multiset-in-cpp-stl/)是一种类似于集合的关联容器，不同的是多个元素可以有相同的值。

**multiset::emplace()**

该函数用于向多集容器中插入新元素。

**语法:**

```cpp
*multisetname*.emplace(*value*)
Parameters :
The element to be inserted into the multiset
is passed as the parameter.
Result :
The parameter is added to the multiset.

```

示例:

```cpp
Input  : mymultiset{1, 2, 3, 4, 5};
         mymultiset.emplace(6);
Output : mymultiset = 1, 2, 3, 4, 5, 6

Input  : mymultiset{};
         mymultiset.emplace("This");
         mymultiset.emplace("is");
         mymultiset.emplace("Geeksforgeeks");
Output : mymultiset = Geeksforgeeks, This, is 

```

**错误和异常**
1。它具有很强的异常保证，因此，如果抛出异常
2，则不会进行任何更改。参数应该与容器的类型相同，否则会引发错误

```cpp
// INTEGER EXAMPLE
// CPP program to illustrate
// Implementation of emplace() function
#include <iostream>
#include <set>
using namespace std;

int main()
{
    multiset<int> mymultiset{};
    mymultiset.emplace(1);
    mymultiset.emplace(56);
    mymultiset.emplace(4);
    mymultiset.emplace(9);
    mymultiset.emplace(0);
    // multi set becomes 0, 1, 4, 9, 56

    // adding another element
    mymultiset.emplace(87);

    // printing the multiset
    for (auto it = mymultiset.begin();
         it != mymultiset.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
0 1 4 9 56 87

```

```cpp
// STRING EXAMPLE
// CPP program to illustrate
// Implementation of emplace() function
#include <iostream>
#include <set>
#include <string>
using namespace std;

int main()
{
    multiset<string> mymultiset{};
    mymultiset.emplace("This");
    mymultiset.emplace("is");
    mymultiset.emplace("a");
    mymultiset.emplace("computer science");
    mymultiset.emplace("portal");
    // multi set becomes This, a,
    // computer science, is, portal

    // adding element
    mymultiset.emplace("GeeksForGeeks");

    // printing the multiset
    for (auto it = mymultiset.begin();
         it != mymultiset.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
GeeksForGeeks This a computer science is portal

```

**应用**
使用侵位()函数输入一个空的多集合，输入以下数字和顺序，求元素的和。与 insert 相比，侵位()的优点是，它避免了不必要的对象复制。

```cpp
Input :  7, 9, 4, 6, 2, 5, 3
Output : 36
```

```cpp
// CPP program to illustrate
// Application of emplace() function
#include <iostream>
#include <set>
using namespace std;

int main()
{
    // sum variable declaration
    int sum = 0;

    // multiset declaration
    multiset<int> mymultiset{};
    mymultiset.emplace(7);
    mymultiset.emplace(9);
    mymultiset.emplace(4);
    mymultiset.emplace(6);
    mymultiset.emplace(2);
    mymultiset.emplace(5);
    mymultiset.emplace(3);

    // iterator declaration
    set<int>::iterator it;

    // finding sum of elements
    while (!mymultiset.empty()) {
        it = mymultiset.begin();
        sum = sum + *it;
        mymultiset.erase(it);
    }

    // printing the sum
    cout << sum;
    return 0;
}
```

输出:

```cpp
36

```

**时间复杂度:** O(logn)

**侵位()vs insert()**
当我们使用 insert 时，我们创建一个对象，然后将其插入到多集合中。通过定位()，对象被就地构建。

```cpp
// C++ code to demonstrate difference between
// emplace and insert
#include<bits/stdc++.h>
using namespace std;

int main()
{
    // declaring multiset of pairs
    multiset<pair<char, int>> ms;

    // using emplace() to insert pair in-place
    ms.emplace('a', 24);

    // Below line would not compile
    // ms.insert('b', 25);    

    // using insert() to insert pair in-place
    ms.insert(make_pair('b', 25));    

    // printing the multiset
    for (auto it = ms.begin(); it != ms.end(); ++ it)
        cout << " " << (*it).first << " " 
             << (*it).second << endl;

    return 0;
}
```

输出:

```cpp
 a 24
 b 25

```

详见[在 std::map 中插入元素(插入、就位和操作员[])](https://www.geeksforgeeks.org/inserting-elements-in-stdmap-insert-emplace-and-operator/) 。