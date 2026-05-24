# 无序集合运算符 `!=` 在 C++ STL 中

> 原文: [https://www.geeksforgeeks.org/unordered_set-operator-in-c-stl-2/](https://www.geeksforgeeks.org/unordered_set-operator-in-c-stl-2/)

`!=` 是 C++ STL 中的一个关系运算符，用来比较无序集合容器之间的等式和不等式。比较按照以下程序进行：

1.  首先，比较大小。
2.  然后，一个容器中的每个元素在另一个容器中查找。

**语法：**

```cpp
unordered_set1 != unordered_set2
```

**参数：** 该方法将两个无序集合容器 `unordered_set1` 和 `unordered_set2` 作为待检查是否相等的参数。
**返回值：** 此方法返回

*   `true`：如果运算符左侧和右侧的无序集容器不相等。
*   `false`：如果运算符左右两边的无序集合容器相等。

下面的例子说明了 `!=` 运算符：

## 示例

```cpp
// C++ program to illustrate
// unordered_set operator!=

#include <cstring>
#include <iostream>
#include <unordered_set>
using namespace std;

int main()
{
    unordered_set<string>
        a = { "C++", "Java", "Python" },
        b = { "Java", "Python", "C++" },
        c = { "C#", "Python", "Java" };

    if (a != b) {
        cout << "a and b are not equal\n";
    }
    else {
        cout << "a and b are equal\n";
    }

    if (a != c) {
        cout << "a and c are not equal\n";
    }
    else {
        cout << "a and c are equal\n";
    }

    return 0;
}
```

**Output:**

```cpp
a and b are equal
a and c are not equal
```