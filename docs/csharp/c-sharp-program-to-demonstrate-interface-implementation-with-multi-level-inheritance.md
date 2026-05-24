# 演示多级继承接口实现的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-程序-演示-接口-实现-多级继承/](https://www.geeksforgeeks.org/c-sharp-program-to-demonstrate-interface-implementation-with-multi-level-inheritance/)

[**多级继承**](https://www.geeksforgeeks.org/c-sharp-multilevel-inheritance/) 是将父类扩展到一个级别的子类的过程。在这种类型的继承中，一个子类将继承一个父类，并且子类也作为创建的其他类的父类。比如三个叫 P，Q，R 的类，其中 R 类衍生自 Q 类，Q 类衍生自 P 类。

**语法**:

```cs
class P : Q
{
    // Methods
}
```

[**界面**](https://www.geeksforgeeks.org/c-sharp-interface/) 指定一个类必须做什么，而不是怎么做。它是班级的蓝图。类似于类，接口也有方法、事件、变量等。但它只包含成员的声明。接口成员的实现将由隐式或显式实现接口的类给出。接口的主要优势是用来实现 100%的抽象。

**语法:**

```cs
interface interface_name
{
    //Method Declaration   
}
```

在理解了多级继承和接口之后，现在我们用多级继承实现接口。为此，我们可以将父类扩展到接口。

```cs
class GFG1 : interface1
{
    // Method definition
    public void MyMethod()
    {
        Console.WriteLine("Parent is called");
    }
}
```

**接近**

> 1.  Create an interface named "interface1" with a method named "MyMethod".
> 2.  Create a parent class named "GFG1" by implementing an interface.
> 3.  Create the first subclass named "GFG2" by extending the parent class.
> 4.  By extending the first subclass, create a second subclass named "GFG3".
> 5.  Create an object in the main method.
> 6.  Use objects to access methods that exist in all classes.

**示例:**

## C#

```cs
// C# program to implement interface 
// with multi-level inheritance
using System;

// Interface
interface interface1
{

    // Method Declaration
    void MyMethod();
}

// Parent class
class GFG1 : interface1
{

    // Method definition
    public void MyMethod()
    {
        Console.WriteLine("Hey! This is Parent");
    }
}

// First child extends parent class
class GFG2 : GFG1
{

    // Method definition
    public void Method1()
    {
        Console.WriteLine("Hey! This is first child");
    }
}

// Second child extends first child
class GFG3 : GFG2
{

    // Method definition
    public void Method2()
    {
        Console.WriteLine("Hey! This is second child");
    }
}

class Geeks{

public static void Main(String[] args)
{

    // Create an object for the second child
    GFG3 obj = new GFG3();

    // Call the methods of patent,
    // first and second child classes
    obj.MyMethod();
    obj.Method1();
    obj.Method2();
}
}
```

**输出:**

```cs
Hey! This is Parent
Hey! This is first child
Hey! This is second child
```