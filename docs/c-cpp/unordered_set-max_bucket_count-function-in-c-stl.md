# c++ STL 中的无序 _ 集合 max_bucket_count()函数

> 原文:[https://www . geesforgeks . org/unordered _ set-max _ bucket _ count-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-max_bucket_count-function-in-c-stl/)

无序集::max_bucket_count()是 C++ STL 中的内置函数，用于查找无序集可以拥有的最大存储桶数。

由于系统指定的约束和一些限制，此函数返回系统可以拥有的最大桶数。

**参数:**该功能不取任何参数。

**语法:**

```cpp
size_type max_bucket_count()
```

其中， **size_type** 为无符号整型。

**返回值:**返回无序集容器可以拥有的*最大桶数*。

**异常:**如果任何元素比较对象抛出异常，就会抛出异常。

下面程序举例说明无序 _ 集合::max_bucket_count()函数:

```cpp
// CPP program to illustrate 
// unordered_set::max_bucket_count() function

#include <iostream>
#include <unordered_set>
using namespace std;

int main()
{
    unordered_set<int> Myset;

    Myset.insert(10);
    Myset.insert(20);

    // printing the contents
    cout<<"Elements : ";
    for (auto it = Myset.begin(); it != Myset.end(); ++ it)
        cout << "[" << *it << "]";
    cout << endl;

    // inspect current parameters
    cout << "max_size : " << Myset.max_size() << endl;
    cout << "max_bucket_count() : " << Myset.max_bucket_count() << endl;
    cout << "max_load_factor() : " << Myset.max_load_factor() << endl;

    return 0;
}
```

**输出:**

```cpp
Elements : [20][10]
max_size : 1152921504606846975
max_bucket_count() : 1152921504606846975
max_load_factor() : 1

```

**输出:**

```cpp
[20][10]
max_size : 1152921504606846975
max_bucket_count() : 1152921504606846975
max_load_factor() : 1
```

**时间复杂度:**执行一个操作需要*恒定的*时间复杂度。