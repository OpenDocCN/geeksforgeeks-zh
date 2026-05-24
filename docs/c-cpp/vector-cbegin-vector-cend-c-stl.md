# c++ STL 中的 vector :: cbegin()和 vector :: cend()

> 原文:[https://www . geesforgeks . org/vector-CBE gin-vector-cend-c-STL/](https://www.geeksforgeeks.org/vector-cbegin-vector-cend-c-stl/)

[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)被称为动态数组，当元素被插入或删除时，它可以自动改变其大小。该存储由容器维护。

**vector::cbegin()**

该函数返回一个迭代器，用于迭代容器。

*   迭代器指向向量的开头。
*   迭代器不能修改向量的内容。

**语法:**

```cpp
*vectorname*.cbegin()

```

> ***参数:***
> *没有参数*
> 
> ***返回值:***
> *常量随机访问迭代器指向向量的开头。*
> 
> ***例外:***
> *无例外*

下面的程序说明了该功能的工作原理

```cpp
// CPP program to illustrate
// use of cbegin()
#include <iostream>
#include <string>
#include <vector>

using namespace std;

int main()
{
    vector<string> vec;

    // 5 string are inserted
    vec.push_back("first");
    vec.push_back("second");
    vec.push_back("third");
    vec.push_back("fourth");
    vec.push_back("fifth");

    // displaying the contents
    cout << "Contents of the vector:" << endl;
    for (auto itr = vec.cbegin(); 
         itr != vec.end(); 
         ++ itr)
        cout << *itr << endl;

    return 0;
}
```

输出:

```cpp
Contents of the vector:
first
second
third
fourth
fifth

```

**vector::cend()**

该函数返回一个迭代器，用于迭代容器。

*   迭代器指向向量的*元素。*
*   *迭代器不能修改向量的内容。*

***语法:***

```cpp
****vectorname*.cend()*** 
```

> ****参数:***
> *没有参数**
> 
> ****返回值:***
> *常量随机访问迭代器指向向量的**元素。****
> 
> ******例外:***
> *无例外****

***下面的程序说明了该功能的工作原理***

```cpp
***// CPP programto illustrate
// functioning of cend()
#include <iostream>
#include <string>
#include <vector>

using namespace std;

int main()
{
    vector<string> vec;

    // 5 string are inserted
    vec.push_back("first");
    vec.push_back("second");
    vec.push_back("third");
    vec.push_back("fourth");
    vec.push_back("fifth");

    // displaying the contents
    cout << "Contents of the vector:" << endl;
    for (auto itr = vec.cend() - 1; 
         itr >= vec.begin(); 
         --itr)
        cout << *itr << endl;

    return 0;
}***
```

***输出:***

```cpp
***Contents of the vector:
fifth
fourth
third
second
first*** 
```