# c++ 中有哪些可以重载和不能重载的运算符？

> 原文:[https://www . geesforgeks . org/什么是 cpp 中可重载和不可重载的运算符/](https://www.geeksforgeeks.org/what-are-the-operators-that-can-be-and-cannot-be-overloaded-in-cpp/)

在 C++ 中，有多种方法可以通过实现以下任何类型的函数来重载运算符:

**1)成员功能**

**2)非成员功能**

**3)好友功能**

**可能超载的运算子清单为:**

<figure class="table">==【T1124】

-【T1214】*

| + | = | < | > |
|  |
| >=【T1128】【t1130 }】 | > |

</figure>

**例 1:重载++ 运算符**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// operators that can be overloaded
#include <iostream>
using namespace std;

class overload {
private:
    int count;

public:
    overload()
        : count(4)
    {
    }

    void operator++() { count = count + 1; }
    void Display() { cout << "Count: " << count; }
};

int main()
{
    overload i;
    // this calls "function void operator ++()" function
    ++ i;
    i.Display();
    return 0;
}
```

**Output**

```cpp
Count: 5
```