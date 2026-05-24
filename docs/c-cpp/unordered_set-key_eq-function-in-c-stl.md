# c++ STL 中的无序 _set key_eq()函数

> 原文:[https://www . geesforgeks . org/unordered _ set-key _ eq-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-key_eq-function-in-c-stl/)

**无序 _set key_eq()** 是 **C++ STL** 中的内置函数，根据比较返回布尔值。它返回无序集使用的键等价比较谓词。键等价比较是一个谓词，它接受两个参数并返回一个 bool 值来指示它们是否相等。

**语法:**

```cpp
key_equal key_eq() const
```

**返回值:**该方法返回键相等比较对象。

**时间复杂度:** O(1)

**例 1:**

```cpp
#include <iostream>
#include <string>
#include <unordered_set>
using namespace std;

int main()
{

    // unordered_set ms is created
    unordered_set<string> ms;

    bool res = ms.key_eq()("a", "A");

    cout << "ms.key_eq() is ";

    if (res == 1) {

        cout << "case insensitive";
    }
    else {

        // res is 0 as arguments are not equivalent
        cout << "case sensitive";
    }

    cout << "\n";

    return 0;
}
```

**Output:**

```cpp
ms.key_eq() is case sensitive

```

**例 2:**

```cpp
#include <iostream>
#include <string>
#include <unordered_set>
using namespace std;

int main()
{

    // unordered_set mp is created
    unordered_set<string> mp;

    // the 2 strings are compared
    bool
        r
        = mp.key_eq()(
            "1000 is a huge number",
            "2000 is a huge number");

    cout << "strings are ";

    if (r == 1) {

        cout << "same";
    }
    else {

        // the strings are not same so r=0
        cout << "not same";
    }

    cout << "\n";

    return 0;
}
```

**Output:**

```cpp
strings are not same

```