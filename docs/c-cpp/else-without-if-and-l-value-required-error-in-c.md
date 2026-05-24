# 否则 C 中没有中频和 L 值要求误差

> 原文:[https://www . geesforgeks . org/else-不带-if-and-l-value-required-in-c/](https://www.geeksforgeeks.org/else-without-if-and-l-value-required-error-in-c/)

### 否则没有中频

如果我们在 if 和 else 子句之间写任何东西，就会显示这个错误。

**示例:**

```cpp
#include <stdio.h>

void main()
{
    int a;

    if (a == 2)
        a++ ;

    // due to this line, we will
    // get error as misplaced else.
    printf("value of a is", a);

    else printf("value of a is not equal to 2 ");
}
```

**输出:**

```cpp
prog.c: In function 'main':
prog.c:15:5: error: 'else' without a previous 'if'
     else printf("value of a is not equal to 2 ");
     ^

```

### 需要 l 值

当我们把常量放在=运算符的左边，变量放在它的右边时，就会出现这个错误。

**示例:**

```cpp
#include <stdio.h>

void main()
{
    int a;
    10 = a;
}
```

**输出:**

```cpp
prog.c: In function 'main':
prog.c:6:5: error: lvalue required as left operand of assignment
  10 = a;
     ^

```

**示例 2:** 在第 12 行，它将显示一个错误的 L 值，因为 arr++ 表示 arr=arr+1。这就是普通变量和数组的区别。如果我们写 a=a+1(其中 a 是正常变量)，编译器会知道它的工作，它们不会出错，但是当你写 arr=arr+1(其中 arr 是数组的名称)时，编译器会认为 arr 包含地址以及我们如何更改地址。因此，它将采用 arr 作为地址，左侧将保持不变，因此，它将显示所需的 L 值错误。

```cpp
#include <stdio.h>

void main()
{
    int arr[5];
    int i;
    for (i = 0; i < 5; i++) {
        printf("Enter number: ");
        scanf("%d", arr);
        arr++ ;
    }
}
```

**输出:**

```cpp
prog.c: In function 'main':
prog.c:10:6: error: lvalue required as increment operand
   arr++ ;
      ^

```