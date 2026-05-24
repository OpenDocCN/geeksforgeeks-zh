# C# 程序演示结构中的静态构造函数

> 原文:[https://www . geeksforgeeks . org/c-sharp-程序演示结构中的静态构造函数/](https://www.geeksforgeeks.org/c-sharp-program-to-demonstrate-the-static-constructor-in-the-structure/)

A [**结构**](https://www.geeksforgeeks.org/c-sharp-structures-set-1/) 是一个定义明确的数据结构，可以容纳多种数据类型的元素。它类似于类，因为两者都是用户定义的数据类型，并且都包含一堆不同的数据类型。您也可以使用预定义的数据类型。但是，有时用户可能需要定义自己的数据类型，也称为用户定义的数据类型。结构还可以保存构造函数、常数、字段、方法、属性和索引器等。我们可以通过使用 struct 关键字后跟结构名称来创建一个结构。

**语法:**

> 公共结构结构名称
> 
> {
> 
> //结构的主体
> 
> }

A [**静态构造函数**](https://www.geeksforgeeks.org/c-sharp-constructors/) 是一种在创建结构或类的第一个实例之前被调用的构造函数。它是用结构的静态字段或数据初始化的，是只执行一次的。我们可以通过使用 static 关键字并后跟构造函数名称来创建一个静态构造函数。

**语法**:

> 静态类()
> 
> {
> 
> //静态构造函数的主体
> 
> }

给定一个结构，现在我们的任务是在给定的结构中使用静态构造函数。所以对此，我们必须遵循以下方法。

**接近**

> *   Create a building called GFG.
> *   Create a static structure with no parameters inside.
> 
> ```cs
> public struct class
> {
>     static class()
>     {
>         // Constructor body
>     }
> }
> ```
> 
> *   Create a non-static method named GFG by passing an integer parameter.
> *   Assign variables in a separate method inside the structure to call the non-static constructor.
> *   In the main method, create an object for the structure, and access the static and non-static methods by creating the object.

**示例:**

## C#

```cs
// C# program to illustrate how to use the 
// static constructor in the structure
using System;

// Create a structure
public struct GFG
{

    // Static method names GFG
    static GFG()
    {
        Console.WriteLine("Hello! Static constructor is called");
    }

    // Non static method
    public GFG(int variable)
    {
        Console.WriteLine("Hello! Non-Static constructor is called");
    }
}

// Driver code
class Geeks{

static void Main(string[] args)
{

    // Create the object for 
    // the structure 
    GFG obj = new GFG(2);
}
}
```

**输出:**

```cs
Hello ! Static constructor is  called
Non-Static constructor is called
```