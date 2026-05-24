# c++ STL 中的无序 _set begin()函数

> 原文:[https://www . geesforgeks . org/unordered _ set-begin-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-begin-function-in-c-stl/)

**无序集::begin()** 方法是 C++ STL 中的一个内置函数，用于返回指向无序集容器中第一个元素的迭代器。无序集的所有迭代器只能用来访问元素，迭代器不允许修改无序集容器中的元素。

**注意**:这个迭代器可以指向无序集容器中任何指定桶的第一个元素或者第一个元素。

**语法** :

```cpp
unordered_set_name.begin(n)
```

**参数**:这是可选参数，指定桶号。如果没有传递这个参数，那么 begin()方法将返回一个指向容器第一个元素的迭代器，如果传递了这个参数，那么 begin()方法将返回一个指向无序集容器中特定桶的第一个元素的迭代器。

**返回值**:这个函数返回一个迭代器，指向容器中的第一个元素或者容器中的指定桶。

下面程序举例说明*无序 _ 集合::begin()* 功能:

```cpp
// CPP program to illustrate the
// unordered_set::begin() function

#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{

    unordered_set<int> sampleSet;

    // Inserting elements in the std
    sampleSet.insert(5);
    sampleSet.insert(10);
    sampleSet.insert(15);
    sampleSet.insert(20);
    sampleSet.insert(25);

    auto itr1 = sampleSet.begin();
    auto itr2 = sampleSet.begin(4);

    cout << "First element in the container is: " << *itr1;
    cout << "\nFirst element in the bucket 4 is: " << *itr2;

    return 0;
}
```

T5】输出:

```cpp
First element in the container is: 25
First element in the bucket 4 is: 15

```