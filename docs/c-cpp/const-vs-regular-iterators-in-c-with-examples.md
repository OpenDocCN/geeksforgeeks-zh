# c++ 中常量与正则迭代器的比较，示例

> 原文:[https://www . geesforgeks . org/const-vs-regular-iterators-in-c-with-examples/](https://www.geeksforgeeks.org/const-vs-regular-iterators-in-c-with-examples/)

**先决条件:**[STL 中的迭代器](https://www.geeksforgeeks.org/iterators-c-stl/)

迭代器是类似于指针的对象，用于遍历序列并操作容器元素。使用迭代器的优点是它将代码行减少到一条语句，因为它们允许我们使用指针作为迭代器来操作 [STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 中的内置数组。迭代器可以是常量，也可以是非常量/正则迭代器。

#### 常量迭代器:

一个**常量迭代器**指向一个常量类型的元素，这意味着常量迭代器所指向的元素不能被修改。虽然我们仍然可以更新迭代器(也就是说，迭代器可以增加或减少，但是它所指向的元素不能改变)。只能用于访问，不能用于修改。如果我们试图使用常量迭代器修改元素的值，那么它会产生一个[错误](https://www.geeksforgeeks.org/program-error-signals/)。

#### **常规迭代器:**

一个**常规或非常量迭代器**指向容器内的一个元素，并可用于修改它所指向的元素。常规迭代器在连接算法和容器以及处理存储在容器中的数据方面起着至关重要的作用。正则迭代器最明显的形式是指针。
指针可以指向[数组](https://www.geeksforgeeks.org/introduction-to-arrays/)中的元素，并可以使用[增量运算符(++)](https://www.geeksforgeeks.org/pre-increment-and-post-increment-in-c/) 对其进行迭代。每个[容器](https://www.geeksforgeeks.org/containers-cpp-stl/)类型都有一个特定的常规迭代器类型，用于遍历其元素。

下面是一个 [C++ 程序](https://www.geeksforgeeks.org/c-plus-plus/)来演示这两个迭代器的工作差异:

## C++

```cpp
// C++ program to demonstrate a regular
// and const_iterator
#include <iostream>
#include <iterator>
#include <vector>
using namespace std;

// Function that demonstrate regular
// iterators
void regularIterator(vector<int>& v)
{
    // Declare a regular iterator
    // to a vector
    vector<int>::iterator i;

    // Printing the elements of the
    // vector v using regular iterator
    for (i = v.begin(); i < v.end(); i++) {

        // Update elements of vector
        *i += 1;
        cout << *i << " ";
    }
}

// Function that demonstrate const
// iterators
void constIterator(vector<int>& v1)
{
    // Declare a const_itearor
    // to a vector
    vector<int>::const_iterator ci;

    // Printing the elements of the
    // vector v1 using regular iterator
    for (ci = v1.begin(); ci < v1.end(); ci++) {

        // Below line will throw an error
        // as we are trying to modify the
        // element to which const_iterator
        // is pointing

        //*ci += 1;

        cout << *ci << " ";
    }
}

// Driver Code
int main()
{
    // Declaring vectors
    vector<int> v = { 7, 2, 4 };
    vector<int> v1 = { 5, 7, 0 };

    // Demonstrate Regular iterator
    regularIterator(v);

    cout << endl;

    // Demonstrate Const iterator
    constIterator(v1);
    return 0;
}
```

**Output:**

```cpp
8 3 5
5 7 0

```