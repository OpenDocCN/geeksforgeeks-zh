# c++ STL 中 fill()函数示例

> 原文:[https://www . geesforgeks . org/fill-function-in-c-STL-with-examples/](https://www.geeksforgeeks.org/fill-function-in-c-stl-with-examples/)

C++ STL 中的 fill()函数用于填充容器中的一些默认值。fill()函数也可用于填充容器中某个范围内的值。它接受两个迭代器*开始*和*结束*，并从*开始*所指的位置开始并刚好在*结束*所指的位置之前填充容器中的值。

**语法** :

```cpp
void fill(iterator begin, iterator end, type value);

```

**参数** :

*   **Start** : The function will start to fill in the value from the position pointed by the iterator *start* .
*   **End** : This function fills the value to the position before the position pointed by the end of the iterator *.*
*   **Value** : This parameter indicates the value to be filled by the function in the container.

**注意**:注意‘开始’包含在范围内，但‘结束’不包含在内。

**返回值**:该函数不返回值。

下图程序说明了 C++ STL 中的 fill()函数:

```cpp
// C++ program to demonstrate working of fill()
#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> vect(8);

    // calling fill to initialize values in the
    // range to 4
    fill(vect.begin() + 2, vect.end() - 1, 4);

    for (int i = 0; i < vect.size(); i++)
        cout << vect[i] << " ";

    // Filling the complete vector with value 10
    fill(vect.begin(), vect.end(), 10);

    cout << endl;

    for (int i = 0; i < vect.size(); i++)
        cout << vect[i] << " ";

    return 0;
}
```

**输出:**

```cpp
0 0 4 4 4 4 4 0 
10 10 10 10 10 10 10 10

```

**参考**:[http://www.cplusplus.com/reference/algorithm/fill/](http://www.cplusplus.com/reference/algorithm/fill/)