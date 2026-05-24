# c++ STL 中的无序 _ 映射重散列

> 原文:[https://www . geesforgeks . org/unordered _ map-rehash-in-c-STL/](https://www.geeksforgeeks.org/unordered_map-rehash-in-c-stl/)

**STD::unordered _ map::rehash()**是一个内置函数 C++ STL，它将容器中的桶数设置为 n 个或更多。
**语法**

```cpp
void rehash( size_type s );

```

*   如果 s 大于容器中的当前桶数，则重新灰化。新存储桶计数可以大于或等于 n。
*   如果 s 小于当前存储桶计数，则可能有也可能没有任何功能影响。这完全取决于编译器

**参数:**将新数量的铲斗装入容器。

**返回类型:**其返回类型为无。

**示例-1:**

```cpp
// C++ code to illustrate the method
// unordered_map rehash
#include <bits/stdc++.h>

using namespace std;

int main()
{
    unordered_map<char, int> sample;

    // Map initialization
    sample = { { 'a', 2 }, { 'b', 4 }, { 'c', 6 } };

    cout << " Size of container : " << sample.size() << endl;
    cout << " Initial bucket count : " << sample.bucket_count() << endl;

    // changing rehash

    sample.rehash(30);
    cout << " Size of container : " << sample.size() << endl;
    cout << " Now bucket count is :  " << sample.bucket_count() << endl;
    return 0;
}
```

**Output:**

```cpp
Size of container : 3
 Initial bucket count : 5
 Size of container : 3
 Now bucket count is :  31

```

**示例-2:**

```cpp
// C++ code to illustrate the method
// unordered_map rehash
#include <bits/stdc++.h>

using namespace std;

int main()
{
    unordered_map<int, int> sample;

    // Map initialization
    sample = { { 2, 2 }, { 3, 4 }, { 4, 6 }, { 5, 8 } };

    cout << " Size of container : " << sample.size() << endl;
    cout << " Initial bucket count : " << sample.bucket_count() << endl;

    // changing rehash

    sample.rehash(20);
    cout << " Size of container : " << sample.size() << endl;
    cout << " Now bucket count is :  " << sample.bucket_count() << endl;
    return 0;
}
```

**Output:**

```cpp
Size of container : 4
 Initial bucket count : 7
 Size of container : 4
 Now bucket count is :  23

```