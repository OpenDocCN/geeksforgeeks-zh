# c++ 中的枚举类及其相对于枚举数据类型的优势

> 原文:[https://www . geesforgeks . org/enum-class-in-c-及其相对于 enum-datatype 的优势/](https://www.geeksforgeeks.org/enum-classes-in-c-and-their-advantage-over-enum-datatype/)

[**枚举或枚举类型(枚举)**](https://www.geeksforgeeks.org/enumerated-types-or-enums-in-c/) 是用户定义的数据类型，可以分配一些有限的值。这些值由程序员在声明枚举类型时定义。

**需要枚举类而不是枚举类型:**
以下是关于枚举类型的局限性以及我们为什么需要枚举类来覆盖它们的一些原因。

**两个**枚举**不能同名:**T4】

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Defining enum1 Gender
    enum Gender { Male,
                  Female };

    // Defining enum2 Gender2 with same values
    // This will throw error
    enum Gender2 { Male,
                   Female };

    // Creating Gender type variable
    Gender gender = Male;
    Gender2 gender2 = Female;

    cout << gender << endl
         << gender2;

    return 0;
}
```