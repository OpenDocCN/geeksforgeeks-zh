# c++ STL 中向量的默认值

> 原文:[https://www . geesforgeks . org/c-STL 中矢量的默认值/](https://www.geeksforgeeks.org/default-value-of-vector-in-c-stl/)

[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)与[动态数组](https://www.geeksforgeeks.org/how-do-dynamic-arrays-work/)相同，能够在插入或删除元素时自动调整自身大小，其存储由容器自动处理。向量元素被放在连续的存储中，这样就可以使用迭代器访问和遍历它们。默认情况下，追加元素时向量的大小会自动改变。

使用随机默认值初始化地图的方法如下:
**方法:**

1.  声明一个向量。
2.  将向量的大小设置为用户定义的大小 N

**向量默认值:**

向量的默认值为 **0** 。

**语法:**

```cpp
// For declaring 
vector v1(size); 

// For Vector with default value 0
vector v1(5);

```

下面是上述方法的实现:

```cpp
// C++ program to create an empty
// vector with default value

#include <bits/stdc++.h>
using namespace std;

int main()
{
    int n = 3;

    // Create a vector of size n with
    // all values as 0.
    vector<int> vect(n);

    for (int x : vect)
        cout << x << " ";

    return 0;
}
```

**Output:**

```cpp
0 0 0

```

**指定向量的默认值:**

我们还可以为向量指定一个随机默认值。为了做到这一点，以下是方法:

**语法:**

```cpp
// For declaring 
vector v(size, default_value);

// For Vector with a specific default value
// here 5 is the size of the vector
// and  10 is the default value
vector v1(5, 10);

```

下面是上述方法的实现:

```cpp
// C++ program to create an empty vector
// and with a specific default value

#include <bits/stdc++.h>
using namespace std;

int main()
{
    int n = 3;
    int default_value = 10;

    // Create a vector of size n with
    // all values as 10.
    vector<int> vect(n, default_value);

    for (int x : vect)
        cout << x << " ";

    return 0;
}
```

**Output:**

```cpp
10 10 10

```