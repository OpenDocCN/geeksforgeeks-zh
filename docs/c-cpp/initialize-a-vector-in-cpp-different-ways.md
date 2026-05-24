# 用 C++ 初始化一个向量(6 种不同的方式)

> 原文:[https://www . geesforgeks . org/initialize-a-vector-in-CPP-differential-way/](https://www.geeksforgeeks.org/initialize-a-vector-in-cpp-different-ways/)

以下是在 C++ STL
中创建和初始化[向量的不同方法](https://www.geeksforgeeks.org/vector-in-cpp-stl/)

**1。逐值初始化:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to create an empty vector
// and push values one by one.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Create an empty vector
    vector<int> vect;

    vect.push_back(10);
    vect.push_back(20);
    vect.push_back(30);

    for (int x : vect)
        cout << x << " ";

    return 0;
}
```

输出:

```cpp
10 20 30
```

**2。指定大小并初始化所有值:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to create an empty vector
// and push values one by one.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int n = 3;

    // Create a vector of size n with
    // all values as 10.
    vector<int> vect(n, 10);

    for (int x : vect)
        cout << x << " ";

    return 0;
}
```

输出:

```cpp
10 10 10
```

**3。初始化类似数组:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to initialize a vector like
// an array.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> vect{ 10, 20, 30 };

    for (int x : vect)
        cout << x << " ";

    return 0;
}
```

输出:

```cpp
10 20 30
```

**4。从数组初始化:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to initialize a vector from
// an array.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int arr[] = { 10, 20, 30 };
    int n = sizeof(arr) / sizeof(arr[0]);

    vector<int> vect(arr, arr + n);

    for (int x : vect)
        cout << x << " ";

    return 0;
}
```

输出:

```cpp
10 20 30
```

**5。从另一个向量初始化:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to initialize a vector from
// another vector.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> vect1{ 10, 20, 30 };

    vector<int> vect2(vect1.begin(), vect1.end());

    for (int x : vect2)
        cout << x << " ";

    return 0;
}
```

输出:

```cpp
10 20 30
```

**6。用特定值初始化所有元素:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> vect1(10);
    int value = 5;
    fill(vect1.begin(), vect1.end(), value);
    for (int x : vect1)
        cout << x << " ";
}
```

输出:

```cpp
5 5 5 5 5 5 5 5 5 5
```

本文由 **Kartik** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。