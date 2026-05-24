# c++ 中不同类型的基于范围的循环迭代器

> 原文:[https://www . geeksforgeeks . org/不同类型的基于范围的循环迭代器 in-c/](https://www.geeksforgeeks.org/different-types-of-range-based-for-loop-iterators-in-c/)

[基于范围的“for”循环](https://www.geeksforgeeks.org/range-based-loop-c/)从 C++ 11 开始就包含在语言中了。它自动迭代(循环)可迭代(容器)。当与标准库容器一起使用时，这是非常有效的(正如本文将使用的)，因为在可迭代范围之外不会有对内存的错误访问。循环将自动在正确的地方开始和结束。

**语法:**

```cpp
for ( range_declaration : range_expression ) 
    loop_statement
```

有三种不同类型的基于范围的“for”循环迭代器，它们是:

**1。普通迭代器:**
在普通迭代器中，一个普通的临时变量被声明为迭代器，迭代器通过值获取当前循环项**的副本。对临时副本所做的任何更改都不会反映在原始副本中。**

**语法:**

```cpp
for (datatype iterator : list)
{
  // operation are performed here 
}
```

*   使用的**迭代器**是任何数据类型的普通迭代器，如 int、float、double 等，用于迭代任何类型的容器。
*   **列表**可以是任何类型的容器。

下面是基于正常范围的迭代器的实现:

## C++

```cpp
// C++ program to implements
// normal iterators

#include <iostream>
#include <vector>
using namespace std;

// Function to implements
// normal iterators
void normal_iterator(vector<int> my_iterable)
{

    // Printing the iterable before making
    // any changes
    cout << "Value before modification: ";
    for (int my_iterator : my_iterable) {
        cout << my_iterator << " ";
    }

    // Case where the iterator
    // makes a temporary copy
    // of the current loop item
    for (int my_iterator : my_iterable) {
        // changing the value of the iterator
        my_iterator += 1;
    }

    cout << "\nValue after modification : ";

    // Printing the iterable
    // to see if any changes
    // has been made in the
    // original container or not
    for (int my_iterator : my_iterable) {
        cout << my_iterator << " ";
    }
}
// Driver Code
int main()
{
    // Initialising a standard
    // template container
    vector<int> my_iterable;
    my_iterable.push_back(101);
    my_iterable.push_back(102);
    my_iterable.push_back(103);
    my_iterable.push_back(104);

    normal_iterator(my_iterable);

    return 0;
}
```

**Output:**

```cpp
Value before modification: 101 102 103 104 
Value after modification : 101 102 103 104
```

**2。引用迭代器:**
引用迭代器被声明为[引用变量](https://www.geeksforgeeks.org/references-in-c/)，迭代器通过引用获取当前项**的值。因此，在循环内部所做的更改肯定会受到原始容器本身的影响。**

**语法:**

```cpp
for (datatype & iterator : list)
{
  // operation are performed here 
}
```

*   使用的**迭代器**是任何数据类型的普通迭代器，如 int、float、double 等，用于迭代任何类型的容器。
*   **列表**可以是任何类型的容器。

下面是基于正常范围的迭代器的实现:

## C++

```cpp
// C++ program to implements
// reference iterators

#include <iostream>
#include <vector>
using namespace std;

// Function to implements
// reference iterators
void reference_iterator(vector<int> my_iterable)
{

    // Printing the iterable before
    // making any changes
    cout << "Value before modification: ";
    for (int my_iterator : my_iterable) {
        cout << my_iterator << " ";
    }

    // Iterating the container
    // using reference iterator
    // and updating the value
    for (int& my_iterator : my_iterable) {

        my_iterator += 1;
    }

    cout << "\nValue after modification : ";
    for (int my_iterator : my_iterable) {
        cout << my_iterator << " ";
    }
}

// Driver Code
int main()
{
    // Initialising a standard
    // template container
    vector<int> my_iterable;
    my_iterable.push_back(101);
    my_iterable.push_back(102);
    my_iterable.push_back(103);
    my_iterable.push_back(104);

    reference_iterator(my_iterable);

    return 0;
}
```

**Output:**

```cpp
Value before modification: 101 102 103 104 
Value after modification : 102 103 104 105
```

**3。常量迭代器:**
常量迭代器被声明为 [**对常量**](https://www.geeksforgeeks.org/different-ways-to-use-const-with-reference-to-a-pointer-in-c/) 的引用，在这种情况下，不会复制当前循环项，与上述两种情况相比，执行速度更快。这在我们不希望迭代器值发生任何意外变化的情况下，或者在我们对容器中的大项进行迭代的情况下非常有用。如果我们试图修改现有的值，那么编译器将显示错误。

**语法:**

```cpp
for (const datatype iterator : list)
{
  // operation are performed here 
}
```

*   使用的**迭代器**是任何数据类型的普通迭代器，如 int、float、double 等，用于迭代任何类型的容器。
*   **列表**可以是任何类型的容器。

下面是基于正常范围的迭代器的实现:

## C++

```cpp
// C++ program to implements
// constant iterators

#include <iostream>
#include <vector>
using namespace std;

// Function to implements
// constant iterators
void reference_iterator(vector<int> my_iterable)
{

    // Printing the iterable
    // using constant iterator
    for (const int& my_iterator : my_iterable) {

        cout << my_iterator << " ";

        // Uncomment below line to see the error
        // my_iterator += 1 ;
    }
}

// Driver Code
int main()
{
    // Initialising a standard
    // template container
    vector<int> my_iterable;
    my_iterable.push_back(101);
    my_iterable.push_back(102);
    my_iterable.push_back(103);
    my_iterable.push_back(104);

    reference_iterator(my_iterable);

    return 0;
}
```

**Output:**

```cpp
101 102 103 104
```