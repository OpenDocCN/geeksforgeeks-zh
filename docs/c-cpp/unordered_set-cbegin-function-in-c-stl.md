# c++ STL 中的无序集 cbegin()函数

> 原文:[https://www . geesforgeks . org/unordered _ set-CBE gin-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-cbegin-function-in-c-stl/)

**无序集::cbegin()** 方法是 C++ STL 中的内置函数，用于返回指向无序集容器中第一个元素的 *const_iterator* 。这个迭代器可以指向无序集容器中任何指定桶的第一个元素。

**注意**:const _ iterator 只能用来访问元素，它不能修改容器中存在的元素。

**语法**:

```cpp
*unordered_set_name*.cbegin(n)

```

**参数**:本功能接受单个参数 **n** 。这是一个可选参数，用于指定桶号。如果未传递此参数，则 cbegin()方法将返回指向容器第一个元素的 const_iterator，如果传递了此参数，则 begin()方法将返回指向无序集容器中特定桶的第一个元素的 const_iterator。

**返回值**:这个函数返回一个指向容器中第一个元素或者容器中指定桶的 const_iterator。

以下程序说明了*无序 _ 集合::cbegin()* 功能:

**程序 1** :

```cpp
// C++ program to illustrate the
// unordered_set::cbegin() function

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

    auto itr1 = sampleSet.cbegin();
    auto itr2 = sampleSet.cbegin(4);

    cout << "First element in the container is: " << *itr1;
    cout << "\nFirst element in the bucket 4 is: " << *itr2;

    return 0;
}
```

**Output:**

```cpp
First element in the container is: 25
First element in the bucket 4 is: 15

```

**程序 2** :

```cpp
// C++ program to illustrate the
// unordered_set::cbegin() function

#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{

    unordered_set<string> sampleSet;

    // Inserting elements
    sampleSet.insert("Welcome");
    sampleSet.insert("To");
    sampleSet.insert("GeeksforGeeks");
    sampleSet.insert("Computer Science Portal");
    sampleSet.insert("For Geeks");

    auto itr1 = sampleSet.cbegin();
    auto itr2 = sampleSet.cbegin(0);

    cout << "First element in the container is: " << *itr1;
    cout << "\nFirst element in the bucket 0 is: " << *itr2;

    return 0;
}
```

**Output:**

```cpp
First element in the container is: Welcome
First element in the bucket 0 is: GeeksforGeeks

```