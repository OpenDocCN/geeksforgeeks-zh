# 使用 C++ 中 STL 函数返回的指针计算索引

> 原文:[https://www . geesforgeks . org/computing-index-using-pointers-returned-STL-functions-c/](https://www.geeksforgeeks.org/computing-index-using-pointers-returned-stl-functions-c/)

C++ 中的许多内置函数将指针返回到内存中给出所需数字地址的位置，但与计算值容器中的实际索引无关。例如，要在代码中找到最大元素，我们使用 [std::max_element()](https://www.geeksforgeeks.org/stdmax_element-in-cpp/) ，它返回内存中的地址，而不是所需元素的索引。

```cpp
// C++ code to demonstrate return value of
// max_element()
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initializing vector
    vector<int> vi = { 1, 4, 5, 6, 3 };

    // printing max element
    cout << "The max element is : " 
         << (*max_element(vi.begin(), vi.end()));

    // printing position
    // prints position in memory
    cout << "\not_eqThe position of maximum element is : ";
    printf("%d", max_element(vi.begin(), vi.end()));
}
```

输出:

```cpp
The max element is : 6
The position of maximum element is : 9583660

```

需要有方法来计算指定容器中所需元素位置的精确索引。本文已经讨论了这些方法。

**减去第一个迭代器**

在这个方法中，我们只需**减去容器的开始指针**，在向量的情况下，它的“ **begin()** ”迭代器指向容器第一个元素的地址，减去这个我们就可以得到容器所需值的精确索引。

```cpp
// C++ code to demonstrate ways to print exact 
// position by subtracting 1st address
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initializing vector
    vector<int> vi = { 1, 4, 5, 6, 3 };

    // printing max element
    cout << "The max element is : " 
         << (*max_element(vi.begin(), vi.end()));

    // printing position
    // prints wanted position
    cout << "\nThe position of maximum element is : ";
    printf("%d", max_element(vi.begin(), 
                vi.end()) - vi.begin());
    return 0;
}
```

输出:

```cpp
The max element is : 6
The position of maximum element is : 3

```

使用[**STD::distance()**](https://www.geeksforgeeks.org/stddistance-in-c/)T5】

使用 distance()也是计算所需位置的另一种方法，方法是将**第一个迭代器作为第一个参数**，将**所需位置作为第二个参数**。

```cpp
// C++ code to demonstrate ways to print exact 
// position using distance()
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initializing vector
    vector<int> vi = { 1, 4, 5, 6, 3 };

    // printing max element
    cout << "The max element is : " 
         << (*max_element(vi.begin(), vi.end()));

    // printing position
    // prints wanted position
    cout << "\nThe position of maximum element is : ";
    printf("%d", distance(vi.begin(), 
                max_element(vi.begin(), vi.end())));
    return 0;
}
```

输出:

```cpp
The max element is : 6
The position of maximum element is : 3

```