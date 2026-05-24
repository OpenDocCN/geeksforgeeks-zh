# c++ STL 中的多集 get _ 分配器()函数

> 原文:[https://www . geesforgeks . org/multist-get _ 分配器-function-in-c-stl/](https://www.geeksforgeeks.org/multiset-get_allocator-function-in-c-stl/)

C++ STL 中的**多集::get _ 分配器()**方法是 C++ STL 中的内置函数，它返回与多集关联的分配器对象的副本。

**语法**:

```cpp
multiset_name.get_allocator()
```

其中**分配器 _type** 是容器使用的分配器的类型。

**参数**:函数不取任何参数。

**返回值**:该方法返回用于构造容器的*分配器对象*。

以下程序说明了多集::get _ 分配器()函数:
**程序 1** :

```cpp
// CPP code to illustrate multiset::get_allocator

#include <iostream>
#include <set>
using namespace std;

int main()
{
    multiset<int> mymultiset;
    int* p;
    unsigned int i;

    // allocate an array of 5 elements
    // using myset's allocator:
    p = mymultiset
            .get_allocator()
            .allocate(5);

    // assign some values to array
    p[0] = 10;
    p[1] = 10;
    p[2] = 20;
    p[3] = 30;
    p[4] = 20;

    cout << "The allocated array contains: ";
    for (i = 0; i < 5; i++) {

        cout << p[i] << " ";
    }
    cout << endl;

    mymultiset.get_allocator().deallocate(p, 5);

    return 0;
}
```

**Output:**

```cpp
The allocated array contains: 10 10 20 30 20

```