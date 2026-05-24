# c++ STL 中的无序 _set cend()函数

> 原文:[https://www . geesforgeks . org/unordered _ set-cend-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-cend-function-in-c-stl/)

**无序集::cend()** 方法是 C++ STL 中的内置函数，用于返回指向无序集容器或其中一个桶中的*结束*元素的*常量迭代器*。该函数不直接指向容器中的任何元素。它仅用于表示容器的末端或范围的开放端，如[cbegin，cend。

**注意**:const _ iterator 只能用来访问元素，它不能修改容器中存在的元素。

**语法**:

```cpp
*unordered_set_name*.cend(n);

```

**参数**:本功能接受单个参数 **n** 。这是一个可选参数，用于指定桶号。如果没有传递这个参数，那么 cend()方法将返回一个 const_iterator，指向容器最后一个元素之后的位置，如果传递了这个参数，那么 cend()方法将返回一个 const_iterator，指向无序集容器中特定桶的最后一个元素之后的位置。

**返回值**:这个函数返回一个 const_iterator，指向容器中最后一个元素或者容器中一个指定桶之后的位置。

以下程序说明了*无序 _ 集合::cend()* 功能:

**程序 1** :

```cpp
// C++ program to illustrate the
// unordered_set::cend() function

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

    // Here, the cend() method is used to
    // iterate in the range of elements
    // present in the unordered_set container
    cout << "Elements present in sampleSet are: \n";
    for (auto itr = sampleSet.cbegin(); itr != sampleSet.cend();
         itr++) {
        cout << *itr << endl;
    }

    return 0;
}
```

**Output:**

```cpp
Elements present in sampleSet are: 
25
5
10
15
20

```

**程序 2** :

```cpp
// C++ program to illustrate the
// unordered_set::cend() function

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

    // Here, the cend() method is used to
    // iterate in the range of elements
    // present in the unordered_set container
    cout << "Elements present in sampleSet are: \n";
    for (auto itr = sampleSet.cbegin(); itr != sampleSet.cend();
         itr++) {
        cout << *itr << endl;
    }

    return 0;
}
```

**Output:**

```cpp
Elements present in sampleSet are: 
Welcome
To
GeeksforGeeks
For Geeks
Computer Science Portal

```