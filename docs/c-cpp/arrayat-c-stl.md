# c++ STL 中的数组::at()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/arrayat-c-STL/

[数组](https://www.geeksforgeeks.org/array-class-c/)类一般比 C 风格数组更高效、轻量、可靠。从 C++ 11 引入数组类为 C 风格的数组提供了一个更好的选择。

**数组::at()**
该函数用于返回对存在于**位置**的元素的引用，该位置作为函数的参数给出。

**语法:**

```cpp
array_name.at(position)

Parameters:
Position of the element to be fetched.

```

**返回:**返回给定位置元素的引用。

**示例:**

```cpp
Input:  array_name1 = [1, 2, 3]
        array_name1.at(2);
Output: 3

Input:  array_name2 = ['a', 'b', 'c', 'd', 'e']
        array_name2.at(4);
Output: e

```

```cpp
// CPP program to illustrate
// Implementation of at() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Take any two array
    array<int, 3> array_name1;
    array<char, 5> array_name2;

    // Inserting values
    for (int i = 0; i < 3; i++)
        array_name1[i] = i+1;

    for (int i = 0; i < 5; i++)
        array_name2[i] = 97+i;

    // Printing the element 
    cout << "Element present at position 2: " 
         << array_name1.at(2) << endl;
    cout << "Element present at position 4: " 
         << array_name2.at(4);

    return 0;
}
```

输出:

```cpp
Element present at position 2: 3
Element present at position 4: e

```

**时间复杂度:**常数，即 O(1)。

**应用:**
给定一个整数数组，从第一个位置开始以交替方式打印整数。

```cpp
Input:  1, 2, 3, 4, 5, 6, 7, 8, 9, 10
Output: 2 4 6 8 10

```

```cpp
// CPP program to illustrate
// application of at() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Declare array
    array<int, 10> a;

    // Inserting values
    for (int i = 0; i < 10; i++)
        a[i] = i+1;

    for (int i = 0; i < a.size(); ++ i) {
        if (i % 2 != 0) {
            cout << a.at(i);
            cout << " ";
        }
    }
    return 0;
}
```

**输出:**

```cpp
2 4 6 8 10 

```