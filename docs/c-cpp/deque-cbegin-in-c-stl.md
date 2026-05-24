# c++ STL 中的 deque CBE gin()

> 原文:[https://www.geeksforgeeks.org/deque-cbegin-in-c-stl/](https://www.geeksforgeeks.org/deque-cbegin-in-c-stl/)

**德克尔**中的 **cbegin()** 方法是 C++ STL 中的一个函数，它返回一个指向容器第一个元素的迭代器。

**语法**:

```cpp
deque_name.cbegin()
```

**返回值**:返回一个常量**迭代器**，指向 deque 的第一个元素。这意味着迭代器可以用来遍历队列，但不能修改它。也就是说，像 insert、erase 这样的函数，如果使用常量迭代器调用，会抛出一个错误。
当您不想让代码的任何部分修改 deque 的内容时，应该使用常量迭代器。

以下程序说明了该功能。

**程序 1:**

```cpp
#include <deque>
#include <iostream>

using namespace std;

int main()
{

    // Create a deque
    deque<int> dq = { 2, 5, 7, 8, 6 };

    // Print the first element of deque
    // using cbegin() method
    cout << "First element of the deque is: ";

    // Get the iterator pointing to the first element
    // And dereference it
    cout << *dq.cbegin();
}
```

**Output:**

```cpp
First element of the deque is: 2

```

**程序 2:**

```cpp
#include <deque>
#include <iostream>

using namespace std;

int main()
{

    // Create a deque
    deque<int> dq = { 1, 5, 2, 4, 7 };

    // Insert an element at the front
    dq.push_front(45);

    // Insert an element at the back
    dq.push_back(56);

    // Print the first element of deque
    // using cbegin() method
    cout << "First element of the deque is: ";

    // Get the iterator pointing to the first element
    // And dereference it
    cout << *dq.cbegin();
}
```

**Output:**

```cpp
First element of the deque is: 45

```