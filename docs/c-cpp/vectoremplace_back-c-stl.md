# 向量::C++ STL 中的 posit _ back

> 哎哎哎:# t0]https://www . geeksforgeeks . org/vectorace _ back-c-STL/

[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)与动态数组相同，能够在插入或删除元素时自动调整自身大小，其存储由容器自动处理。

**vector::emplace_back()**

这个函数用来在向量容器中插入一个新元素，新元素被添加到向量的末尾。
**语法:**

```cpp
*vectorname*.emplace_back(*value*)
Parameters :
The element to be inserted into the vector
is passed as the parameter.
Result :
The parameter is added to the
vector at the end position.

```

**示例:**

```cpp
Input: myvector{1, 2, 3, 4, 5};
         myvector.emplace_back(6);
Output: myvector = 1, 2, 3, 4, 5, 6

Input: myvector{};
         myvector.emplace_back(4);
Output: myvector = 4

```

**错误和异常:**

1.  它有很强的异常保证，因此，如果抛出异常，不会进行任何更改。
2.  参数应该与容器的类型相同，否则会引发错误。

**例 1:**

```cpp
// INTEGER VECTOR EXAMPLE
// CPP program to illustrate
// Implementation of emplace() function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> myvector;
    myvector.emplace_back(1);
    myvector.emplace_back(2);
    myvector.emplace_back(3);
    myvector.emplace_back(4);
    myvector.emplace_back(5);
    myvector.emplace_back(6);
    // vector becomes 1, 2, 3, 4, 5, 6

    // printing the vector
    for (auto it = myvector.begin(); it != myvector.end(); ++ it)
        cout << ' ' << *it;

    return 0;

}
```

**输出:**

```cpp
1 2 3 4 5 6

```

**例 2:**

```cpp
// STRING VECTOR EXAMPLE
// CPP program to illustrate
// Implementation of emplace() function
#include <iostream>
#include <vector>
#include <string>
using namespace std;

int main()
{
    // vector declaration
    vector<string> myvector;
    myvector.emplace_back("This");
    myvector.emplace_back("is");
    myvector.emplace_back("a");
    myvector.emplace_back("computer science");
    myvector.emplace_back("portal");

    // vector becomes This, is, a computer science, portal

    // printing the vector
    for (auto it = myvector.begin(); it != myvector.end(); ++ it)
        cout << ' ' << *it;

    return 0;

}
```

**输出:**

```cpp
This is a computer science portal

```

**例 3:**

```cpp
// CHARACTER VECTOR EXAMPLE
// CPP program to illustrate
// Implementation of emplace() function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<char> myvector;
    myvector.emplace_back('a');
    myvector.emplace_back('c');
    myvector.emplace_back('x');
    myvector.emplace_back('y');
    myvector.emplace_back('z');
    // vector becomes a, c, x, y, z

    // printing the vector
    for (auto it = myvector.begin(); it != myvector.end(); ++ it)
        cout << ' ' << *it;

    return 0;

}
```

**输出:**

```cpp
a, c, x, y, z

```

**时间复杂度:** O(1)

**应用:**
给定一个空向量，使用 retain _ back 函数向其添加整数，然后计算其大小。

```cpp
Input  : 1, 2, 3, 4, 5, 6
Output : 6
```

**算法**

1.  使用定位功能向矢量添加元素
2.  检查向量的大小是否为 0，如果不是，递增初始化为 0 的计数器变量，并弹出后元素。
3.  重复此步骤，直到向量的大小变为 0。
4.  打印变量的最终值。

```cpp
// CPP program to illustrate
// Application of emplace_back function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    int count = 0;
    vector<int> myvector;
    myvector.emplace_back(1);
    myvector.emplace_back(2);
    myvector.emplace_back(3);
    myvector.emplace_back(4);
    myvector.emplace_back(5);
    myvector.emplace_back(6);
    while (!myvector.empty()) {
        count++ ;
        myvector.pop_back();
    }
    cout << count;
    return 0;
}
```

**输出:**

```cpp
6
```

**定位 _ 后退()vs 推送 _ 后退()**

1.  **push_back()** 将字符串复制到向量中。首先，将隐式创建一个新的字符串对象，并用提供的 char*进行初始化。然后将调用 push_back，它将使用移动构造函数将该字符串复制到向量中，因为原始字符串是一个临时对象。那么临时对象将被销毁。
2.  **侵位 _back()** 就地构造一个字符串，因此不会创建临时字符串，而是直接用 char*参数调用侵位 _back()。然后，它将创建一个字符串存储在用这个 char*初始化的向量中。因此，在这种情况下，我们避免构造和销毁不必要的临时字符串对象。

详见 C++ STL 中[定位与插入。](https://www.geeksforgeeks.org/emplace-vs-insert-c-stl/)

```cpp
// C++ code to demonstrate difference between
// emplace_back and insert_back
#include<bits/stdc++.h>
using namespace std;

int main()
{
    // declaring priority queue
    vector<pair<char, int>> vect;

    // using emplace() to insert pair in-place
    vect.emplace_back('a', 24);

    // Below line would not compile
    // vect.push_back('b', 25);    

    // using push_back() to insert
    vect.push_back(make_pair('b', 25));    

    // printing the vector
    for (int i=0; i<vect.size(); i++)
        cout << vect[i].first << " " << vect[i].second
             << endl;

    return 0;
}
```

**输出:**

```cpp
a 24
b 25

```