# C++ STL 中的 unordered_map::bucket()

> 原文: [https://www.geeksforgeeks.org/unordered_map-bucket-in-c-stl/](https://www.geeksforgeeks.org/unordered_map-bucket-in-c-stl/)

`unordered_map::bucket()` 是 C++ 中内置的 STL 函数，返回关键字为 `k` 的元素在映射中所处的 bucket 编号。

**语法:**
```cpp
size_type bucket(key)
```

**参数:** 该函数接受一个强制参数 `key`，该键指定要返回其桶号的键。
**返回值:** 这个方法返回一个无符号整数类型，代表参数中传递的密钥 `k` 的桶号。

下面程序举例说明 `unordered_map::bucket()` 函数:

## 示例程序

```cpp
// CPP program to demonstrate the
// unordered_map::bucket() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Declaration
    unordered_map<string, string> mymap;

    // Initialisation
    mymap = { { "Australia", "Canberra" },
              { "U.S.", "Washington" },
              { "France", "Paris" } };

    // prints the bucket number of the beginning element
    auto it = mymap.begin();

    // stores the bucket number of the key k
    int number = mymap.bucket(it->first);
    cout << "The bucket number of key " << it->first
         << " is " << number;

    return 0;
}
```

**输出:**
```cpp
The bucket number of key France is 3
```