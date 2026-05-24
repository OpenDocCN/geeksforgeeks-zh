# C++和Java中布尔数据类型的比较

> 原文：[https://www.geeksforgeeks.org/comparison-boolean-data-type-c-java/](https://www.geeksforgeeks.org/comparison-boolean-data-type-c-java/)

布尔数据类型是C++和Java中的基本数据类型之一。虽然，它看起来可能是所有数据类型中最简单的，因为它只能有两个值——`true`或`false`，但这肯定是一个棘手的问题，因为它在Java和C++中的使用有一定的差异，如果不小心，可能会导致错误。它在C++和Java中的不同用法是：

## Declaration
布尔数据类型在C++中的声明涉及使用关键字`bool`，而在Java中的声明则通过关键字`boolean`完成。

**C++代码：**
```cpp
#include<iostream>
using namespace std;
int main()
{
    bool a = true;

    // Syntax of Java 
    // boolean b = false;

    return 0;
}
```

**Java代码：**
```java
class A
{
    public static void main(String args[])
    {
        boolean a = true;

        // Syntax of C++
        // bool b = false;
    }
}
```

## Default Value
默认值是变量在声明时但未初始化为任何值时最初存储的值。Java中布尔数据类型的默认值是`false`，而在C++中，它没有默认值，包含的是垃圾值（仅在全局变量的情况下，其默认值将为`false`）。

**C++代码：**
```cpp
#include<iostream>
using namespace std;
int main()
{
    // Declaring a boolean type array in C++
    bool a[5];

    int i;
    for (i=0; i<5; ++i)
    {
        cout << a[i] << " ";
    }
    return 0;
}
```
上述程序中数组中存储的所有值都是垃圾值，不是固定的。

**Java代码：**
```java
class A
{
    public static void main(String args[])
    {
        // Declaring a boolean type array in Java
        boolean a[];
        a = new boolean[5];

        int i;
        for(i=0; i<5; ++i)
        {
            System.out.println(a[i]);
        }
    }
}
```
输出：
```
false
false
false
false
false
```
数组`a`中的所有值默认为`false`，如上图所示。

## Use in Mathematical Expressions
一个重要的区别是，布尔数据类型变量不能在Java的数学表达式中使用，因为这会给出错误，而在C++中则可以轻松使用。

这种行为的原因是布尔变量在Java中没有被转换成整数值（0或1），所以它们不能这样使用。

**C++代码：**
```cpp
#include<iostream>
using namespace std;
int main()
{
    int a;
    bool b = true;
    bool c = false;
    a = b + c;
    cout << a;
    return 0;
}
```
输出：
```
1
```
输出将为1，因为`true`将被转换为值1，`false`将被转换为值0，所以`a`将存储1，而相同的代码在Java中将给出一个错误，如下所示。

**Java代码：**
```java
class A
{
    public static void main(String args[])
    {
        int a;
        boolean b = true;
        boolean c = false;

        //The following line will give an error
        a = b + c;

        System.out.println(a);
    }
}
```

## Use with Relational Operators
在Java中，布尔变量不能与关系运算符如`<`、`>`、`<=`和`>=`一起使用，而在C++中，它们可以以这种方式使用。**然而，它们可以在Java和C++中与`==`和`!=`运算符一起使用。**

这可以归因于这样一个事实，即关系运算符对数值进行操作，布尔变量在Java中不是作为数值存储的，而是在C++中这样存储的（`false`存储为0，`true`存储为1）。

**C++代码：**
```cpp
#include<iostream>
using namespace std;
int main()
{
    bool a = true;
    bool b = false;
    if (a > b)
    {
        cout << "a is greater than b";  
    }    
    else
    {
        cout << "a is smaller than b";
    }    
    return 0;
}
```
输出：
```
a is greater than b
```

**Java代码：**
```java
class a
{
    public static void main(String args[])
    {
        boolean a = true;
        boolean b = false;

        //The following line will give an error
        if (a > b)
        {         
            System.out.println("a is greater than b");
        }
        else
        { 
            System.out.println("a is smaller than b");
        }
    }
}
```

## Floating point value
在C++中，浮点、整数值可以轻松地赋值给布尔变量，因为它们将被隐式类型转换为布尔值，而在Java中这样做将导致错误。

**C++代码：**
```cpp
#include<iostream>
using namespace std;
int main()
{
    // storing integer value in bool type variable
    bool a = 7;

    // storing floating value in bool type variable
    bool b = 7.0;

    cout << a << " " << b;
    return 0;
}
```
输出：
```
1 1
```
上面的输出结果是将任何值存储在一个布尔变量中，而不是0，将导致1存储在该变量中。

**Java代码：**
```java
class a
{
    public static void main(String args[])
    {
        // invalid assignment in Java
        boolean a = 7;

        // invalid assignment in Java    
        boolean b = 7.0;

        System.out.println(a);
        System.out.println(b);
    }
}
```

## Size
C++中布尔数据类型的大小是1字节，而Java中布尔值的大小没有精确定义，它取决于Java虚拟机（JVM）。

Java中的布尔值总是需要一个以上的字节，但是更多的字节取决于值存储在哪里——在堆栈中，还是在堆中。JVM使用32位堆栈单元，这将导致每个布尔值占据32位的完整堆栈单元。然而，堆上布尔值的大小取决于实现。

本文由**姆里根德拉·辛格**供稿。如果你喜欢GeeksforGeeks并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到`contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。