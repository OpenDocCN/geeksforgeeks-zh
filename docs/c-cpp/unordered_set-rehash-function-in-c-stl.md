# c++ STL 中的无序 _ 集合重散列()函数

> 原文:[https://www . geesforgeks . org/unordered _ set-rehash-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-rehash-function-in-c-stl/)

**无序 _ 集合::rehash()** 是 C++ STL 中的内置函数，用于将无序 _ 集合的容器中的桶数设置为给定大小或更大。如果大小大于容器的当前大小，则调用 rehash。如果小于当前大小，则该函数对哈希的桶计数没有影响。

**语法**:

```cpp
*unordered_set_name.rehash(size_type n)*
```

**参数**:该函数接受一个强制参数 n，该参数指定了容器的最小桶数。

**返回值**:这个函数不返回任何东西。

下面的程序说明了无序集::重散列()函数:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_set::rehash()
#include <iostream>
#include <string>
#include <unordered_set>

using namespace std;

int main()
{
    // declaration
    unordered_set<string> us;

    // rehashed
    us.rehash(9);

    // insert elements
    us.insert("geeks");
    us.insert("for");
    us.insert("geeks");
    us.insert("users");

    for (auto it = us.begin(); it != us.end(); it++) {
        cout << *it << " ";
    }

    cout << "\nThe bucket count is "
         << us.bucket_count();

    return 0;
}
```

**Output:**

```cpp
users for geeks 
The bucket count is 11

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_set::rehash()
#include <iostream>
#include <string>
#include <unordered_set>

using namespace std;

int main()
{
    // declaration
    unordered_set<string> us;

    // rehash the unordered_set
    us.rehash(20);

    // insert strings
    us.insert("geeks");
    us.insert("for");
    us.insert("geeks");
    us.insert("users");
    us.insert("are");
    us.insert("experts");
    us.insert("in");
    us.insert("DS");

    // prints the elements
    for (auto it = us.begin(); it != us.end(); it++) {
        cout << *it << " ";
    }

    cout << "\nThe bucket count is "
         << us.bucket_count();

    return 0;
}
```

**Output:**

```cpp
DS in experts are users for geeks 
The bucket count is 23

```