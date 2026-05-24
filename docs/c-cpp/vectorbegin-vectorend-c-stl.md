# c++ STL 中的 vector::begin()和 vector::end()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/vector begin-vector-c-STL/

[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)与动态数组相同，能够在插入或删除元素时自动调整自身大小，其存储由容器自动处理。

**vector::begin()**

begin()函数用于返回指向向量容器第一个元素的迭代器。begin()函数**返回一个双向迭代器**到容器的第一个元素。
**语法:**

```cpp
***vectorname***.begin()
Parameters :
No parameters are passed.
Returns :
This function returns a bidirectional
iterator pointing to the first element.

```

示例:

```cpp
Input  : myvector{1, 2, 3, 4, 5};
         myvector.begin();
Output : *returns an iterator to the element 1*

Input  : myvector{"This", "is", "Geeksforgeeks"};
         myvector.begin();
Output : *returns an iterator to the element This*

```

**错误和异常**
1。它有一个无异常抛出保证。
2。传递参数时显示错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// INTEGER VECTOR EXAMPLE
// CPP program to illustrate
// Implementation of begin() function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    // declaration of vector container
    vector<int> myvector{ 1, 2, 3, 4, 5 };

    // using begin() to print vector
    for (auto it = myvector.begin();
         it != myvector.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

**输出:**

```cpp
1 2 3 4 5

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// STRING VECTOR EXAMPLE
// CPP program to illustrate
// Implementation of begin() function
#include <iostream>
#include <string>
#include <vector>
using namespace std;

int main()
{
    // declaration of vector container
    vector<string> myvector{ "This", "is",
                             "Geeksforgeeks" };

    // using begin() to print vector
    for (auto it = myvector.begin();
         it != myvector.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

**输出:**

```cpp
This is Geeksforgeeks

```

**时间复杂度:** O(1)

**vector::end()**

end()函数用于返回指向向量容器最后一个元素的迭代器。end()函数**返回一个双向迭代器**。
**语法:**

```cpp
***vectorname***.end()
Parameters :
No parameters are passed.
Returns :
This function returns a bidirectional
iterator pointing to next to last element.

```

示例:

```cpp
Input  : myvector{1, 2, 3, 4, 5};
         myvector.end();
Output : *returns an iterator after 5*

Input  : myvector{"computer", "science", "portal"};
         myvector.end();
Output : *returns an iterator after**portal* 
```

**错误和异常**
1。它有一个无异常抛出保证。
2。传递参数时显示错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// INTEGER VECTOR EXAMPLE
// CPP program to illustrate
// Implementation of end() function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    // declaration of vector container
    vector<int> myvector{ 1, 2, 3, 4, 5 };

    // using end() to print vector
    for (auto it = myvector.begin();
         it != myvector.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

**输出:**

```cpp
1 2 3 4 5

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// STRING VECTOR EXAMPLE
// CPP program to illustrate
// Implementation of end() function
#include <iostream>
#include <string>
#include <vector>
using namespace std;

int main()
{
    // declaration of vector container
    vector<string> myvector{ "computer",
                             "science", "portal" };

    // using end() to print vector
    for (auto it = myvector.begin();
         it != myvector.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

**输出:**

```cpp
computer science portal

```

**时间复杂度:** O(1)