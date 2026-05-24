# C 中的匿名并集和结构

> 原文:[https://www . geesforgeks . org/g-fact-38-anonymous-union-and-structure/](https://www.geeksforgeeks.org/g-fact-38-anonymous-union-and-structure/)

在 C 的 [C11](https://en.wikipedia.org/wiki/C11_(C_standard_revision)) 标准中，增加了匿名并集和结构。
匿名工会/结构也称为未命名工会/结构，因为它们没有名称。因为没有名字，所以不创建它们的直接对象(或变量)，我们在嵌套结构或联合中使用它们。
定义就像没有名字和标签的正常结合。例如，

```cpp
// Anonymous union example
union 
{
   char alpha;
   int num;
};
```

```cpp
// Anonymous structure example
struct 
{
   char alpha;
   int num;
};
```

由于没有变量也没有名字，我们可以直接访问成员。这种可访问性仅在定义匿名联合的范围内有效。
下面是一个完整的匿名工会工作示例。

## C

```cpp
// C Program to demonstrate working of anonymous union
#include <stdio.h>
struct Scope {
    // Anonymous union
    union {
        char alpha;
        int num;
    };
};

int main()
{
    struct Scope x, y;
    x.num = 65;
    y.alpha = 'A';

    // Note that members of union are accessed directly
    printf("y.alpha = %c, x.num = %d", y.alpha, x.num);

    return 0;
}
```

请记住，我们一次只能访问一个工会成员。如果分配了另一个成员，前一个成员将从工会中被清除。

**Output**

```cpp
x.alpha = A, x.num = 65
```