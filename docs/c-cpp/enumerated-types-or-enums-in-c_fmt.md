# C++ 中的枚举类型或枚举

> 原文：[https://www.geeksforgeks.org/enumerated-types-or-enums-in-c/](https://www.geeksforgeeks.org/enumerated-types-or-enums-in-c/)

**枚举类型**（`enum`）是一种用户自定义的数据类型，可以分配一些有限的值。这些值由程序员在声明枚举类型时定义。

当我们在字符值中赋值一个浮点值时，编译器会以同样的方式产生一个错误。如果我们试图给枚举数据类型赋值，编译器会产生一个错误。枚举数类型的值也称为枚举数。它也由零赋值，与数组相同。它也可以与 `switch` 语句一起使用。

**例如：** 如果用值 `Male` 或 `Female` 创建了 `Gender` 变量。如果分配了除 `Male` 或 `Female` 以外的任何其他值，则不合适。在这种情况下，可以声明只分配 `Male` 和 `Female` 值的枚举类型。

**语法：**

> `enum` *枚举类型名称* `{value1, value2, value3…..valueN };`

`enum` 关键字用于在枚举类型名称被写入之后声明枚举类型，然后在花括号下定义可能的值。定义枚举类型后，创建变量。它可以创建为两种类型：

1.  它可以在声明枚举类型的过程中声明，只需在分号前添加变量的名称。
2.  除此之外，我们可以创建与普通变量相同的枚举类型变量。

> *枚举类型名称* *变量名称* = *值*;

默认情况下，枚举的第一个元素的起始代码值是 `0`（如在数组的情况下）。但是可以明确改变。

**例如：** `enum` *枚举类型名称* `{值1=1, 值2, 值3 };`

并且，枚举的连续值将具有下一组代码值。

**例如：**

```cpp
// first_enum 是枚举类型名称
enum first_enum {value1, value2=10, value3};

In this case, 
first_enum e;
e=value3;
cout<<e;
```

Output:

```
11
```

## 例 1

### 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // 定义枚举 Gender
    enum Gender { Male, Female };

    // 创建 Gender 类型变量
    Gender gender = Male;

    switch (gender)
    {
    case Male:
        cout << "Gender is Male";
        break;
    case Female:
        cout << "Gender is Female";
        break;
    default:
        cout << "Value can be Male or Female";
    }
    return 0;
}
```

**Output:**

```
Gender is Male
```

## 例 2

### 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <bits/stdc++.h>
using namespace std;

// 定义枚举 year
enum year {
    Jan,
    Feb,
    Mar,
    Apr,
    May,
    Jun,
    Jul,
    Aug,
    Sep,
    Oct,
    Nov,
    Dec
};

// 驱动代码
int main()
{
    int i;

    // 遍历 year 枚举
    for (i = Jan; i <= Dec; i++)
        cout << i << " ";

    return 0;
}
```

**Output:**

```
0 1 2 3 4 5 6 7 8 9 10 11
```