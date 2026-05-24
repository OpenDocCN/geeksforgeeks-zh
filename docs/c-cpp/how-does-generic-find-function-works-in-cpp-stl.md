# 泛型 find()函数在 C++ STL 中是如何工作的？

> 原文:[https://www . geesforgeks . org/how-to-generic-find-function-works-in-CPP-STL/](https://www.geeksforgeeks.org/how-does-generic-find-function-works-in-cpp-stl/)

**find():**[**find()**功能](https://www.geeksforgeeks.org/std-find-in-cpp/)用于[搜索给定范围内的元素](https://www.geeksforgeeks.org/searching-algorithms/)，每个 [STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) [容器](https://www.geeksforgeeks.org/containers-cpp-stl/)都具有使用 **find()** 功能搜索元素的功能。通用查找功能适用于每种[数据类型](https://www.geeksforgeeks.org/c-data-types/)。

**返回类型:**

*   它将一个[迭代器](https://www.geeksforgeeks.org/iterators-c-stl/)返回到范围**【第一个，最后一个】**中的第一个元素，该元素等于给定的**键**。
*   如果没有找到这样的元素，函数将迭代器返回到最后一个元素。

**进场:**

*   [不同](https://www.geeksforgeeks.org/vector-in-cpp-stl/)[数据类型](https://www.geeksforgeeks.org/c-data-types/)的向量，如 **int** 、 **string** 等，取了一个关键元素。
*   基于关键元素的搜索功能被调用。
*   使用[模板](https://www.geeksforgeeks.org/templates-cpp/)编写搜索功能的工作机制。
*   该函数基于关键元素搜索矢量从**开始**到**结束**的元素。如果该值不存在，那么它将返回**结束迭代器**。
*   如果关键元素与向量元素匹配，那么它将返回元素及其位置。

下面是 [C++ 程序](https://www.geeksforgeeks.org/c-plus-plus/)来说明泛型 **find()** 在 vector 中的实现:

## C++

```cpp
// C++ program to illustrate the
// implementation of generic find()
#include <iostream>
#include <vector>
using namespace std;

// Two generic templates classes one
// for iterator and other for key
template <class ForwardIterator, class T>
ForwardIterator search(
    ForwardIterator start,
    ForwardIterator end, T key)
{
    while (start != end) {

        // If key is present then return
        // the start iterator
        if ((*start) == key) {
            return start;
        }

        // Increment the iterator
        start++ ;
    }

    // If key is not present then,
    // return end iterator
    return end;
}

// Function to illustrate the use
// of generic find()
void inputElements()
{
    // Vector of integer data type
    vector<int> v{ 10, 20, 40, 30, 50 };

    // Element to be searched
    int key = 100;

    // Stores the address
    auto it = search(v.begin(), v.end(),
                     key);

    if (it != v.end()) {

        cout << key << " is present"
             << " at position "
             << it - v.begin() + 1
             << endl;
    }
    else {

        cout << key
             << " is not present"
             << endl;
    }

    cout << endl;

    // Vector of string data type
    vector<string> str{ "C++", "Python",
                        "GFG", "Ruby" };

    // Element to be searched
    string key2 = "GFG";

    // Stores the address
    auto it2 = search(str.begin(), str.end(),
                      key2);

    if (it2 != str.end()) {

        cout << key2 << " is present "
             << "at position "
             << it2 - str.begin() + 1
             << endl;
    }
    else {

        cout << key2 << " is not Present"
             << endl;
    }
}

// Driver Code
int main()
{
    // Function Call
    inputElements();

    return 0;
}
```

**Output:**

```cpp
100 is not present

GFG is present at position 3

```