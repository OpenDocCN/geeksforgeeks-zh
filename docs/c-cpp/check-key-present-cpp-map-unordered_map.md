# 检查 C++ 映射或无序映射中是否存在键

> 原文:[https://www . geesforgeks . org/check-key-present-CPP-map-无序 _map/](https://www.geeksforgeeks.org/check-key-present-cpp-map-unordered_map/)

一个 [C++ 映射](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)和[无序 _ 映射](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/)被初始化为一些键和它们各自的映射值。
示例:

```cpp
Input : 
Map : 1 -> 4, 2 -> 6, 4 -> 6
Check1 : 5, Check2 : 4
Output : 5 : Not present, 4 : Present
```

C++ 实现:

## 地图

```cpp
// CPP code to check if a
// key is present in a map
#include <bits/stdc++.h>
using namespace std;

// Function to check if the key is present or not
string check_key(map<int, int> m, int key)
{
    // Key is not present
    if (m.find(key) == m.end())
        return "Not Present";

    return "Present";
}

// Driver
int main()
{
    map<int, int> m;

    // Initializing keys and mapped values
    m[1] = 4;
    m[2] = 6;
    m[4] = 6;

    // Keys to be checked
    int check1 = 5, check2 = 4;

    // Function call
    cout << check1 << ": " << check_key(m, check1) << '\n';
    cout << check2 << ": " << check_key(m, check2);
}
```

## 无序地图

```cpp
// CPP code to check if a key is present
// in an unordered_map
#include <bits/stdc++.h>
using namespace std;

// Function to check if the key is present or not
string check_key(unordered_map<int, int> m, int key)
{
    // Key is not present
    if (m.find(key) == m.end())
        return "Not Present";

    return "Present";
}

// Driver
int main()
{
    unordered_map<int, int> m;

    // Initialising keys and mapped values
    m[1] = 4;
    m[2] = 6;
    m[4] = 6;

    // Keys to be checked
    int check1 = 5, check2 = 4;

    // Function call
    cout << check1 << ": " << check_key(m, check1) << '\n';
    cout << check2 << ": " << check_key(m, check2);
}
```

输出:

```cpp
5: Not Present
4: Present
```

**接近 2 档:**

我们也可以在 c++ 中使用 map 的 count 函数。

**实施:**

**1。地图**

## C++

```cpp
// CPP code to check if a
// key is present in a map
#include <bits/stdc++.h>
using namespace std;

// Function to check if the key is present or not using count()
string check_key(map<int, int> m, int key)
{
    // Key is not present
    if (m.count(key) == 0)
        return "Not Present";

    return "Present";
}

// Driver
int main()
{
    map<int, int> m;

    // Initializing keys and mapped values
    m[1] = 4;
    m[2] = 6;
    m[4] = 6;

    // Keys to be checked
    int check1 = 5, check2 = 4;

    // Function call
    cout << check1 << ": " << check_key(m, check1) << '\n';
    cout << check2 << ": " << check_key(m, check2);
}
```

**输出:**

> 5:不在场
> 
> 4:出席

**2。无序地图**

## C++

```cpp
// CPP code to check if a key is present
// in an unordered_map
#include <bits/stdc++.h>
using namespace std;

// Function to check if the key is present or not using count()
string check_key(unordered_map<int, int> m, int key)
{
    // Key is not present
    if (m.count(key) == 0)
        return "Not Present";

    return "Present";
}

// Driver
int main()
{
    unordered_map<int, int> m;

    // Initialising keys and mapped values
    m[1] = 4;
    m[2] = 6;
    m[4] = 6;

    // Keys to be checked
    int check1 = 5, check2 = 4;

    // Function call
    cout << check1 << ": " << check_key(m, check1) << '\n';
    cout << check2 << ": " << check_key(m, check2);
}
```

**输出:**

> 5:不在场
> 
> 4:出席

本文由 **Rohit Thapliyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。