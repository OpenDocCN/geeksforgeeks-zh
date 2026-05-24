# c++ STL 中的无序 _ 集合 find()函数

> 原文:[https://www . geesforgeks . org/unordered _ set-find-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-find-function-in-c-stl/)

**无序 _ 集合::find()** 函数是 C++ STL 中的内置函数，用于搜索容器中的元素。它返回元素的迭代器，如果找到了 else，它返回一个指向无序集::end()的迭代器。

**语法**:

```cpp
*unordered_set_name*.find(key)
```

**参数**:该功能接受一个强制参数*键*，指定要搜索的元素。

**返回值**:如果找到元素就返回一个迭代器，否则返回一个指向无序集结尾的迭代器。

以下程序说明了*无序 _ 集合::find()* 功能:

**程序 1** :

```cpp
// C++ program to illustrate the
// unordered_set::find() function

#include <iostream>
#include <string>
#include <unordered_set>

using namespace std;

int main()
{

    unordered_set<string> sampleSet = { "geeks1", "for", "geeks2" };

    // use of find() function
    if (sampleSet.find("geeks1") != sampleSet.end()) {
        cout << "element found." << endl;
    }
    else {
        cout << "element not found" << endl;
    }

    return 0;
}
```

**Output:**

```cpp
element found.

```

**程序 2** :

```cpp
// CPP program to illustrate the
// unordered_set::find() function

#include <iostream>
#include <string>
#include <unordered_set>

using namespace std;

int main()
{

    unordered_set<string> sampleSet = { "geeks1", "for", "geeks2" };

    // use of find() function
    if (sampleSet.find("geeksforgeeks") != sampleSet.end()) {
        cout << "found" << endl;
    }
    else {
        cout << "Not found" << endl;
    }

    return 0;
}
```

**Output:**

```cpp
Not found

```