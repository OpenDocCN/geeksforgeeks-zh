# std :: reverse_copy 在 C++ STL 中

> 原文:[https://www.geeksforgeeks.org/std-reverse_copy-in-c-stl/](https://www.geeksforgeeks.org/std-reverse_copy-in-c-stl/)

C++ STL 提供了一个函数，它从给定的范围复制元素，但顺序相反。下面是一个简单的程序来展示 reverse_copy()的工作原理。

示例:

```cpp
Input : 1 2 3 4 5 6 7 8 9 10
Output : The vector is: 
10 9 8 7 6 5 4 3 2 1

```

该函数接受三个参数。前两个参数是要复制的元素的范围，第三个参数是以相反顺序复制元素的起点。

```cpp
// C++ program to copy from array to vector
// using reverse_copy() in STL.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int src[] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
    int n = sizeof(src) / sizeof(src[0]);

    vector<int> dest(n);

    reverse_copy(src, src + n, dest.begin());

    cout << "The vector is: \n";
    for (int x : dest) {
        cout << x << " ";
    }

    return 0;
}
```

**Output:**

```cpp
The vector is: 
10 9 8 7 6 5 4 3 2 1

```

下面是一个矢量到矢量复制的例子。

```cpp
// C++ program to copy from array to vector
// using reverse_copy() in STL.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> src { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

    vector<int> dest(src.size());

    reverse_copy(src.begin(), src.end(), dest.begin());

    cout << "The vector is: \n";
    for (int x : dest) {
        cout << x << " ";
    }

    return 0;
}
```

**Output:**

```cpp
The vector is: 
10 9 8 7 6 5 4 3 2 1

```