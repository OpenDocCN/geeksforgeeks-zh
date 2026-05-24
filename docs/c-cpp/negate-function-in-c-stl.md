# c++ STL 中的求反函数

> 原文:[https://www.geeksforgeeks.org/negate-function-in-c-stl/](https://www.geeksforgeeks.org/negate-function-in-c-stl/)

该函数用于否定给定值，即改变值的符号。它将正值变为负值，反之亦然。

**注意:**这个类的对象可以在标准算法上使用，比如[变换](https://www.geeksforgeeks.org/transform-c-stl-perform-operation-elements/)。
**语法:**

```cpp
transform(arr_begin, arr_end, arr2_begin, negate()) 
```

**参数:**它接受以下描述的四个参数:

1.  arr_begin:它是给定数组的下限。
2.  arr_end:它是给定数组的上限。
3.  arr2_begin:它是第二个数组的下限，修改后的值将在该数组中更新。
4.  **求反 <datatype>()</datatype>** :是用来求反给定数组值的函数。

**返回值:**返回符号相反的相同值。

下面是显示否定()函数工作原理的实现:

```cpp
// C++ program to show the working 
// of negate() function
#include <algorithm>
#include <functional>
#include <iostream>
using namespace std;
int main()
{
    int arr[] = { 5, 7, -20, -60, 50 };

    // using transform negation of values is done
    transform(arr, arr + 5, arr, negate<int>());

    for (int i = 0; i < 5; i++)
        cout << arr[i] << ' ';

    return 0;
}
```

**Output:**

```cpp
-5 -7 20 60 -50

```