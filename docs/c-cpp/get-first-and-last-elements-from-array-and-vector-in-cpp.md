# 获取 CPP 中数组和向量的第一个和最后一个元素

> 原文:[https://www . geeksforgeeks . org/从 cpp 中的数组和向量中获取第一个和最后一个元素/](https://www.geeksforgeeks.org/get-first-and-last-elements-from-array-and-vector-in-cpp/)

给定一个数组，找到它的第一个和最后一个元素。

```cpp
Input: {4, 5, 7, 13, 25, 65, 98}
Output: First element: 4
Last element: 98

```

在 C++ 中，我们可以使用 [sizeof 运算符](https://www.geeksforgeeks.org/sizeof-operator-c/)来查找数组中的元素数量。

```cpp
// C++ Program to print first and last element in an array
#include <iostream>
using namespace std;
int main()
{
    int arr[] = { 4, 5, 7, 13, 25, 65, 98 };
    int f, l, n;
    n = sizeof(arr) / sizeof(arr[0]);
    f = arr[0];
    l = arr[n - 1];
    cout << "First element: " << f << endl;
    cout << "Last element: " << l << endl;
    return 0;
}
```

**输出:**

```cpp
First element: 4
Last element: 98

```

当数组作为参数传递时，我们不应该 [sizeof，在这里我们必须传递 size 并使用该 size 来查找第一个和最后一个元素。](https://www.geeksforgeeks.org/using-sizof-operator-with-array-paratmeters/)

```cpp
// C++ Program to print first and last element in an array
#include <iostream>
using namespace std;

int printFirstLast(int arr[], int n)
{
    int f = arr[0];
    int l = arr[n - 1];
    cout << "First element: " << f << endl;
    cout << "Last element: " << l << endl;
}

int main()
{
    int arr[] = { 4, 5, 7, 13, 25, 65, 98 };
    int n = sizeof(arr) / sizeof(arr[0]);
    printFirstLast(arr, n);
    return 0;
}
```

**Output:**

```cpp
First element: 4
Last element: 98

```

在 C++ 中[向量的情况下，有像](https://www.geeksforgeeks.org/vector-in-cpp-stl/)[前后](https://www.geeksforgeeks.org/vectorfront-vectorback-c-stl/)这样的函数来寻找第一个和最后一个元素。

```cpp
// C++ Program to find first and last elements in vector
#include <iostream>
#include <vector>
using namespace std;
int main()
{
    vector<int> v;

    v.push_back(4);
    v.push_back(5);
    v.push_back(7);
    v.push_back(13);
    v.push_back(25);
    v.push_back(65);
    v.push_back(98);
    cout << "v.front() is now " << v.front() << '\n';
    cout << "v.back() is now " << v.back() << '\n';
    return 0;
}
```

**输出:**

```cpp
v.front() is now 4
v.back() is now 98

```

即使向量作为参数传递，我们也可以使用前后。