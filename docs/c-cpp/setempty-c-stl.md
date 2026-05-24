# 设置::空()在 C++ STL 中

> 原文:[https://www.geeksforgeeks.org/setempty-c-stl/](https://www.geeksforgeeks.org/setempty-c-stl/)

[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)是一种关联容器，其中每个元素必须是唯一的，因为元素的值标识了它。元素的值一旦添加到集合中就不能修改，尽管可以移除和添加该元素的修改值。

**set::empty()**

empty()函数用于检查集合容器是否为空。

**语法:**

```cpp
*setname*.empty()
Parameters :
No parameters are passed.
Returns :
True, if set is empty
False, Otherwise

```

示例:

```cpp
Input  : myset{1, 2, 3, 4, 5};
         myset.empty();
Output : False

Input  : myset{};
         myset.empty();
Output : True

```

**错误和异常**

1.它有一个无异常抛出保证。
2。传递参数时显示错误。

```cpp
// INTEGER SET
// CPP program to illustrate
// Implementation of empty() function
#include <iostream>
#include <set>
using namespace std;

int main()
{
    // set declaration
    set<int> myset{};

    // checking if set is empty
    if (myset.empty()) {
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

```cpp
// CHARACTER SET
// CPP program to illustrate
// Implementation of empty() function
#include <iostream>
#include <set>
using namespace std;

int main()
{
    // set declaration
    set<char> myset{ 'A', 'b' };

    // checking if set is empty
    if (myset.empty()) {
        cout << "True";
    }
    else {
        cout << "False";
    }
```

输出:

```cpp
False

```

**时间复杂度:** O(1)

**应用:**
给定一组整数，求所有整数的和。

```cpp
Input  : 1, 5, 6, 3, 9, 2
Output : 26
Explanation -  1+5+6+3+9+2 = 26
```

**算法**

1.检查集合是否为空，如果不是，将第一个元素添加到初始化为 0 的变量中，并删除第一个元素。
2。重复此步骤，直到集合为空。
3。打印变量的最终值。

```cpp
// CPP program to illustrate
// Application of empty() function
#include<iostream>
#include<set>

using namespace std;

int main()
{
    // sum variable declaration
    int sum = 0;

    // set declaration
    set<int> myset{ 1, 5, 6, 3, 9, 2 };

    // finding sum of elements
    while(!myset.empty()){
        sum+= *myset.begin();
        myset.erase(myset.begin());
    }

    // print sum
     cout<<sum<<endl;
    return 0;
}
```

输出:

```cpp
26

```