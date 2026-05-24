# C/c++ 中的前增量和后增量

> 原文:[https://www . geesforgeks . org/预增量-和后增量-in-c/](https://www.geeksforgeeks.org/pre-increment-and-post-increment-in-c/)

在 C/C++ 中，增量运算符用于将变量的值增加 1。该运算符由 **++** 符号表示。递增运算符可以在将变量赋值给变量之前将变量的值增加 1，也可以在赋值给变量之后将变量的值增加 1。**因此可以分为两类:**

*   **Preincrement Operator**
*   **Post-increment operator**

**1)预增量运算符**:预增量运算符用于在表达式中使用变量之前对其值进行增量。在预增量中，值首先递增，然后在表达式中使用。

**语法:**

```cpp
 a = ++ x;
```

这里，如果“x”的值是 10，那么“a”的值将是 11，因为“x”的值在表达式中使用之前会被修改。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate pre increment
// operator
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    int x = 10, a;

    a = ++ x;
    cout << "Pre Increment Operation";

    // Value of a will change
    cout << "\na = " << a;

    // Value of x change before execution of a=++ x;
    cout << "\nx = " << x;

    return 0;
}
```

**Output**

```cpp
Pre Increment Operation
a = 11
x = 11
```

**2)后递增运算符**:后递增运算符用于在使用后递增的表达式完全执行后，递增变量的值。在后增量中，值首先在表达式中使用，然后递增。

**语法:**

```cpp
 a = x++ ;
```

这里，假设“x”的值是 10，那么变量“a”的值将是 10，因为使用了“x”的旧值。

## CPP

```cpp
// CPP program to demonstrate post increment
// operator
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    int x = 10, a;

    a = x++ ;

    cout << "Post Increment Operation";

    // Value of a will not change
    cout << "\na = " << a;

    // Value of x change after execution of a=x++ ;
    cout << "\nx = " << x;

    return 0;
}
```

**输出**

```cpp
Post Increment Operation
a = 10
x = 11
```

**后递增运算符的特殊情况:**如果我们将后递增值赋给同一个变量，那么该变量的值将不会递增，即保持不变。

**语法:**

```cpp
a = a++ ;
```

这里，如果“x”的值是 10，那么“a”的值将是 10，因为“x”的值被赋给了递增后的值“x”。

## C++

```cpp
// CPP program to demonstrate special
// case of post increment operator
#include <iostream>
using namespace std;

int main()
{

    int x = 10;

    cout << "Value of x before post-incrementing";

    cout << "\nx = " << x;

    x = x++ ;

    cout << "\nValue of x after post-incrementing";

    // Value of a will not change
    cout << "\nx = " << x;

    return 0;
}
```

**输出:**

```cpp
Value of x before post-incrementing
x = 10
Value of x after post-incrementing
x = 10
```

> **注:**这种特殊情况只适用于后递增和后递减运算符，而前递增和前递减运算符在这种情况下工作正常。

**评估后和预增量一起**

后缀++ 的优先级比前缀++ 高，它们的结合性也不同。前缀++ 的结合性是从右向左，后缀++ 的结合性是从左向右。

*   The relevance of suffix++ is from left to right.
*   The relevance of prefix++ is from right to left.

本文由**苏维克南迪**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。