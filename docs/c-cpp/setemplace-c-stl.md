# 在 C++ STL 中设置::侵位()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/setemplace-c-STL/

[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)是一种关联容器，其中每个元素必须是唯一的，因为元素的值标识了它。元素的值一旦添加到集合中就不能修改，尽管可以移除和添加该元素的修改值。

**set::emplace()**

仅当要插入的元素是唯一的并且不存在于集合中时，此函数用于将新元素插入集合容器。

**语法:**

```cpp
*setname*.emplace(*value*)
Parameters :
The element to be inserted into the set
is passed as the parameter.
Result :
The parameter is added to the set if 
the set does not contain that element already.

```

示例:

```cpp
Input  : myset{1, 2, 3, 4, 5};
         myset.emplace(6);
Output : myset = 1, 2, 3, 4, 5, 6

Input  : myset{1, 2, 3, 4, 5};
         myset.emplace(4);
Output : myset = 1, 2, 3, 4, 5

```

**错误和异常**
1。它具有很强的异常保证，因此，如果抛出异常
2，则不会进行任何更改。参数应该与容器的类型相同，否则会引发错误

```cpp
// INTEGER SET EXAMPLE
// CPP program to illustrate
// Implementation of emplace() function
#include <iostream>
#include <set>
using namespace std;

int main()
{
    set<int> myset{};
    myset.emplace(2);
    myset.emplace(6);
    myset.emplace(8);
    myset.emplace(9);
    myset.emplace(0);
    // set becomes 0, 2, 6, 8, 9

    // adding unique element

    myset.emplace(5);
    // set becomes 0, 2, 5, 6, 8, 9

    // adding element which already
    // exists there will be no
    // change in the set

    myset.emplace(2);
    // set remains 0, 2, 5, 6, 8, 9

    // printing the set
    for (auto it = myset.begin();
         it != myset.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
0 2 5 6 8 9

```

```cpp
// STRING SET EXAMPLE
// CPP program to illustrate
// Implementation of emplace() function
#include <iostream>
#include <set>
#include <string>
using namespace std;

int main()
{
    set<string> myset{};
    myset.emplace("This");
    myset.emplace("is");
    myset.emplace("a");
    myset.emplace("computer science");
    myset.emplace("portal");
    // set becomes This, a, computer
    // science, is, portal

    // adding unique element
    myset.emplace("GeeksForGeeks");
    // set becomes GeeksForGeeks, This, is,
    // a, computer science, portal

    // adding element which already exists
    // there will be no change in the set
    myset.emplace("is");

    // set remains GeeksForGeeks, This, is,
    // a, computer science, portal

    // printing the set
    for (auto it = myset.begin();
         it != myset.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
GeeksForGeeks This a computer science is portal

```

**时间复杂度:** O(logn)

**应用**
使用侵位()函数输入一个空的多集合，输入以下数字和顺序，求元素的和。

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

    // set declaration
    set<int> myset{};
    myset.emplace(7);
    myset.emplace(9);
    myset.emplace(4);
    myset.emplace(6);
    myset.emplace(2);
    myset.emplace(5);
    myset.emplace(3);

    // iterator declaration
    set<int>::iterator it;

    // finding sum of elements
    while (!myset.empty()) {
        it = myset.begin();
        sum = sum + *it;
        myset.erase(it);
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

**定位()vs 插入**
当我们使用插入时，我们创建一个对象，然后将其插入多集。通过定位()，对象被就地构建。

```cpp
// C++ code to demonstrate difference between
// emplace and insert
#include<bits/stdc++.h>
using namespace std;

int main()
{
    // declaring set
    set<pair<char, int>> ms;

    // using emplace() to insert pair in-place
    ms.emplace('a', 24);

    // Below line would not compile
    // ms.insert('b', 25);    

    // using emplace() to insert pair in-place
    ms.insert(make_pair('b', 25));    

    // printing the set
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