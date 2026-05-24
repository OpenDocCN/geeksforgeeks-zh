# c++ STL 中 fill_n()函数示例

> 原文:[https://www . geesforgeks . org/fill _ n-function-in-c-STL-with-examples/](https://www.geeksforgeeks.org/fill_n-function-in-c-stl-with-examples/)

C++ STL 中的 fill_n()函数用于填充容器中的一些默认值。fill_n()函数用于从起始位置开始将值填充到前 n 个位置。它接受一个迭代器*开始*和位置数量 *n* 作为参数，并用给定的*值*填充从*开始*所指向的位置开始的第一个 **n** 位置。

**语法** :

```cpp
void fill_n(iterator begin, int n, type value);

```

**参数** :

*   **Start** : The function will start to fill in the value from the position pointed by the iterator *start* .
*   **n** : this parameter indicates the number of positions to be filled from the position indicated by from the first parameter *.*
*   **Value** : This parameter indicates the value to be filled by the function in the container.

**返回值**:该函数不返回值。

下图程序说明了 C++ STL 中 fill_n()函数:

```cpp
// C++ program to demonstrate working of fil_n()
#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> vect(8);

    // calling fill to initialize first four values
    // to 7
    fill_n(vect.begin(), 4, 7);

    for (int i = 0; i < vect.size(); i++)
        cout << ' ' << vect[i];
    cout << '\n';

    // calling fill to initialize 3 elements from
    // "begin()+3" with value 4
    fill_n(vect.begin() + 3, 3, 4);

    for (int i = 0; i < vect.size(); i++)
        cout << ' ' << vect[i];
    cout << '\n';

    return 0;
}
```

**输出:**

```cpp
7 7 7 7 0 0 0 0
 7 7 7 4 4 4 0 0

```

**参考**:[http://www.cplusplus.com/reference/algorithm/fill_n/](http://www.cplusplus.com/reference/algorithm/fill_n/)