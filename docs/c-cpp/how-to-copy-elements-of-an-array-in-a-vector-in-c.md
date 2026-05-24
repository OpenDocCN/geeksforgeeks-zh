# 如何在 C++ 中复制向量中数组的元素

> 原文:[https://www . geesforgeks . org/如何复制 c 中矢量数组元素/](https://www.geeksforgeeks.org/how-to-copy-elements-of-an-array-in-a-vector-in-c/)

一个 [数组](https://www.geeksforgeeks.org/array-data-structure/) 是存储在连续内存位置的项目集合。想法是将多个相同类型的项目存储在一起。

![Array](img/06ae604a79a0646affeb3b79ae905dcd.png)

[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/) 是与 [相同的动态数组](https://www.geeksforgeeks.org/how-do-dynamic-arrays-work/) ，能够在插入或删除元素时自动调整本身的大小，其存储由容器自动处理。

以下是将元素从数组复制到向量的不同方法:

**方法 1:** **天真解**
[遍历完整数组](https://www.geeksforgeeks.org/c-program-to-traverse-an-array/)并使用 [push_back()](https://www.geeksforgeeks.org/vectorpush_back-vectorpop_back-c-stl/) 函数将每个元素插入到新分配的向量中。以下是上述方法的实施:

## C++

```cpp
// C++ program of the above approach
#include <bits/stdc++.h>
using namespace std;

// Driver code
int main()
{
    // Initialise an array
    int arr[] = { 1, 2, 3, 4, 5 };
    int N = sizeof(arr) / sizeof(arr[0]);

    // Initialize an empty vector
    vector<int> v;

    // Traverse the array and
    for (int i = 0; i < N; i++)
        v.push_back(arr[i]);

    // Print all elements of vector
    for (auto ele : v) {
        cout << ele << " ";
    }

    return 0;
}
```

**Output**

```cpp
1 2 3 4 5 
```

**方法 2:初始化期间基于范围的赋值**
在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中，Vector 类提供了一个[构造函数](https://www.geeksforgeeks.org/constructors-c/)，该构造函数接受一个范围，因此要从数组元素创建一个向量，在向量初始化期间将指向范围的第一个和最后一个位置的指针作为需要复制到向量的参数传递(即 arr，arr+N)。

下面是上述方法的实现:

## C++

```cpp
// C++ program of the above approach
#include <bits/stdc++.h>
using namespace std;

// Driver code
int main()
{
    // Initialise an array
    int arr[] = { 1, 2, 3, 4, 5 };
    int N = sizeof(arr) / sizeof(arr[0]);

    // Initialize a vector by passing the
    // pointer to the first and last element
    // of the range as arguments
    vector<int> v(arr, arr + N);

    // Print all elements of vector
    for (auto ele : v) {
        cout << ele << " ";
    }

    return 0;
}
```

**Output**

```cpp
1 2 3 4 5 
```

注意，也可以使用用于指向 STL 容器内存地址的[迭代器](https://www.geeksforgeeks.org/iterators-c-stl/)。

*   std::begin(arr)-数组第一个元素的迭代器。
*   std::end(arr)-数组最后一个元素之后的迭代器。

> 向量 <int>v(开始(arr)，结束(arr))；</int>

**方法三:使用内置函数 Insert(position，first_iterator，last _ iterator):**[Insert()](https://www.geeksforgeeks.org/vector-insert-function-in-c-stl/)是 [C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 中的内置函数，在指定位置的元素前插入新元素，通过插入的元素数量有效增加容器大小。范围也可以作为参数传递，而不是单个值。

下面是上述方法的实现:

## C++

```cpp
// C++ program of the above approach
#include <bits/stdc++.h>
using namespace std;

// Driver code
int main()
{
    // Initialise an array
    int arr[] = { 1, 2, 3, 4, 5 };
    int N = sizeof(arr) / sizeof(arr[0]);

    // Initialize an empty vector
    vector<int> v;

    // Add array elements in the required
    // range into a vector from beginning
    v.insert(v.begin(), arr, arr + N);

    // Print all elements of vector
    for (auto ele : v) {
        cout << ele << " ";
    }

    return 0;
}
```

**Output**

```cpp
4 6 8 10 12 
```

**方法 4:使用内置函数 Copy(first_iterator，last_iterator，back_inserter()):** 将数组元素复制到向量中的另一种方法是使用内置的 [copy](https://www.geeksforgeeks.org/copy-constructor-in-cpp/) 函数。这个函数接受 3 个参数，一个迭代器到数组的第一个元素，一个迭代器到数组的最后一个元素，back_inserter 函数从后面插入值。

下面是上述方法的实现:

## C++

```cpp
// C++ program of the above approach
#include <bits/stdc++.h>
using namespace std;

// Driver code
int main()
{
    // Initialise an array
    int arr[] = { 1, 2, 3, 4, 5 };
    int N = sizeof(arr) / sizeof(arr[0]);

    // Initialize an empty vector
    vector<int> v;

    // Copy array elements in the required
    // range into vector v using copy function
    copy(begin(arr), end(arr), back_inserter(v));

    // Print all elements of vector
    for (auto ele : v) {
        cout << ele << " ";
    }

    return 0;
}
```

**Output**

```cpp
1 2 3 4 5 
```

**方法 5:使用内置函数赋值(first_iterator，last _ iterator):**[向量::assign()](https://www.geeksforgeeks.org/vector-assign-in-c-stl/) 函数可用于为新向量或现有向量赋值。如果需要，它还可以修改向量的大小。它将迭代器放在第一个和最后一个位置作为参数。

下面是上述方法的实现:

## C++

```cpp
// C++ program of the above approach
#include <bits/stdc++.h>
using namespace std;

// Driver code
int main()
{
    // Initialise an array
    int arr[] = { 1, 2, 3, 4, 5 };
    int N = sizeof(arr) / sizeof(arr[0]);

    // Initialize an empty vector
    vector<int> v;

    // Assign the elements of the array
    // into the vector v
    v.assign(arr, arr + N);

    // Print all elements of vector
    for (auto ele : v) {
        cout << ele << " ";
    }

    return 0;
}
```

**Output**

```cpp
1 2 3 4 5 
```

**方法 6:使用内置函数 Transform(first_iterator，last_iterator，back_insert()，函数):**[STD::Transform()](https://www.geeksforgeeks.org/transform-c-stl-perform-operation-elements/)函数取 4 个参数，一个迭代器到数组的第一个元素，一个迭代器到数组的最后一个元素，back_inserter 函数从后面插入值，以及一个用户自定义函数，可用于修改数组的所有元素，即执行一元运算，将小写字符转换为大写字符等。

下面是上述方法的实现:

## C++ 14

```cpp
// C++ program of the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to increment the value by 1
int increment(int x)
{
    return x + 1;
}

// Driver code
int main()
{
    // Initialise an array
    int arr[] = { 1, 2, 3, 4, 5 };
    int N = sizeof(arr) / sizeof(arr[0]);

    // Initialize an empty vector
    vector<int> v;

    // Copy the elements of the array into
    // vector v and increment each value
    transform(arr, arr + N, back_inserter(v), increment);

    // Print all elements of vector
    for (auto ele : v) {
        cout << ele << " ";
    }

    return 0;
}
```

**Output**

```cpp
2 3 4 5 6 
```