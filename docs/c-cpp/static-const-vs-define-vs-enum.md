# “静态常量”vs“#定义”vs“枚举”

> 原文:[https://www . geesforgeks . org/static-const-vs-define-vs-enum/](https://www.geeksforgeeks.org/static-const-vs-define-vs-enum/)

在本文中，我们将分析**“静态常量”、“#define”和“enum”**。这三个经常令人困惑，选择使用哪一个有时可能是一项困难的任务。

**静态常量**

**static const:**“static const”基本上是 [static](https://www.geeksforgeeks.org/static-variables-in-c/) (一个存储说明符)和 [const](https://www.geeksforgeeks.org/const-qualifier-in-c/) (一个类型限定符)的组合。

**Static :** 决定变量的生存期和可见性/可访问性。这意味着，如果一个变量被声明为静态变量，当程序运行时，它将一直保留在内存中，而当函数(定义该变量的地方)结束时，正常或自动变量将被销毁。
**Const :** 是类型限定词。类型限定符用于通过类型系统表达关于值的附加信息。当使用 const 类型限定符初始化变量时，它将不接受其值的进一步更改。
所以结合 static 和 const，我们可以说当一个变量使用 static const 初始化时，**它将保留它的值直到程序执行，并且它不会接受它的值的任何变化。**

**语法:**

```cpp
static const data_type name_of_variable = initial_value;

```

```cpp
// C++ program to demonstrate the use of
// static const

#include <bits/stdc++.h>

using namespace std;
// function to add constant value to input
int addConst(int input)
{
    // value = 5 will be stored in
    // memory even after the
    // execution of the
    // function is finished
    static const int value = 5;

    // constant_not_static will
    // not accept change in value
    // but it will get destroyed
    // after the execution of
    // function is complete
    const int constant_not_static = 13;
    input += value;

    // value++ ; ==> this statement will produce error
    return input;
}

int main()
{
    int input = 10;
    cout << addConst(input) << endl;

    return 0;
}
```

**Output:**

```cpp
15

```

**“什么是# [定义](https://www.geeksforgeeks.org/typedef-versus-define-c/)”？**

它经常被误解为编程语句。但它实际上是设置了一个**宏**。宏会在编译之前替换文本。要了解更多关于宏的信息，请参考[宏 _ vs _ 函数](https://www.geeksforgeeks.org/macros-vs-functions/)一文。

**语法:**

```cpp
#define token [value]

```

注意:标记不能有空格，值可以有空格。
例:

```cpp
 #define ll long long int
```

```cpp
// C++ program to demonstrate
// the use of #define

#include <bits/stdc++.h>

// defining long long int as => ll
#define ll long long int

// defining for loop
#define f(i, a, b, c) for (ll i = a; i < b; i += c)
using namespace std;

// function to count to a given number
void count(ll input)
{
    // loop implemented using macros
    // for(long long int j=1; j<input+1;j+=1)
    f(j, 1, input + 1, 1)
    {
        cout << j << " ";
    }
    cout << endl;
}

int main()
{
    // ll will get replaced by
    // long long int
    ll num = 10;
    count(num);

    return 0;
}
```

**Output:**

```cpp
1 2 3 4 5 6 7 8 9 10

```

**什么是枚举？**

枚举是用户定义的数据类型。它用于为整型常量赋值，以提高代码的可读性。使用枚举“enum”关键字在 C/C++ 中使用。

**语法:**

```cpp
enum flag{constant1= 2, constant2=3, constant3=4....};

```

“enum”与“#define”的不同之处在于它会自动为变量赋值。在前面的例子中，如果没有赋值= >

```cpp
enum{constant1, constant2, constantd3...}

```

变量将被自动赋值(constant1= 0，constant2= 1，constant3= 2…)。使用枚举代替宏有各种好处。其中之一是自动赋值。

```cpp
// C++ program to demonstrate
// the use of enum

#include <bits/stdc++.h>

using namespace std;

int main()
{
    // declaring weekdays data type
    enum weekdays { mon,
                    tues,
                    wed,
                    thurs,
                    fri,
                    sat,
                    sun };
    // a variable named day1 holds the value of wed
    enum weekdays day1 = wed;

    // mon holds 0, tue holds 1 and so on
    cout << "The value stored in wed is :" << day1 << endl;

    // looping through the values of
    // defined integral constants
    for (int i = mon; i <= sun; i++)
        cout << i << " ";
    cout << endl;

    return 0;
}
```

**Output:**

```cpp
The value stored in wed is :2
0 1 2 3 4 5 6

```

有关枚举的更多信息，请参考 C 文章中的[枚举(或枚举)。](https://www.geeksforgeeks.org/enumeration-enum-c/)