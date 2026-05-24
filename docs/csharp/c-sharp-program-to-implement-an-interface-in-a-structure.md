# 在结构中实现接口的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-程序到实现结构中的接口/](https://www.geeksforgeeks.org/c-sharp-program-to-implement-an-interface-in-a-structure/)

[**【结构】**](https://www.geeksforgeeks.org/c-sharp-structures-set-1/# :~:text=Defining%20Structure%3A%20In%20C%23%2C%20structure,properties%2C%20indexers%20and%20events%20etc.) 是一个值类型和单个单元下不同数据类型的变量集合。它几乎类似于一个类，因为两者都是用户定义的数据类型，并且都持有一堆不同的数据类型。我们可以使用 struct 关键字创建一个结构。结构还可以保存构造函数、常数、字段、方法、属性、索引器和事件等。

**语法:**

```cs
public struct 
{
    // Fields
    // Methods
}
```

[**接口**](https://www.geeksforgeeks.org/c-sharp-interface/) 就像一个类，它也可以有方法、属性、事件和索引器作为它的成员。但是接口只能有成员的声明。接口成员的实现将由隐式或显式实现接口的类给出。或者我们可以说它是班级的蓝图。

**语法**:

```cs
interface interface_name
{
    // Method Declaration in interface
}
```

现在给定这两个接口，现在我们的任务是在一个结构中实现这两个接口。

**进场:**

*   创建两个名为 interface1 和 interface2 的接口，其中包含方法声明。
*   创建一个实现这些接口的结构。

```cs
struct GFG : interface1, interface2
{
    // Method definition for interface method
    // Method definition for interface method
}
```

*   在 GFG 结构中为两个接口编写方法定义。
*   在主方法中，创建两个名为 M1 和 M2 的对象。
*   使用 M1 和 M2 对象调用接口 1 和接口 2 的方法并显示输出。

**示例:**

## C#

```cs
// C# program to illustrate how to implement
// interface in a structure
using System;

// Interface 1
interface interface1
{

    // Declaration of Method
    void MyMethod1();
}

// Interface 2
interface interface2
{

    // Declaration of Method
    void MyMethod2();
}

// Structure which implement interface1
// and interface2
struct GFG : interface1, interface2
{

    // Method definitions of interface 1
    void interface1.MyMethod1()
    {
        Console.WriteLine("interface1.Method() is called");
    }

    // Method definitions of interface 2
    void interface2.MyMethod2()
    {
        Console.WriteLine("interface2.Method() is called");
    }
}

class Geeks{

// Driver code   
public static void Main(String[] args)
{

    // Declare interfaces
    interface1 M1;
    interface2 M2;

    // Create objects
    M1 = new GFG();
    M2 = new GFG();

    M1.MyMethod1();
    M2.MyMethod2();
}
}
```

**输出:**

```cs
interface1.Method() is called
interface2.Method() is called
```