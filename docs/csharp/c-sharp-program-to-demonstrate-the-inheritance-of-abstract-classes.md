# 演示抽象类继承的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-程序演示抽象类的继承/](https://www.geeksforgeeks.org/c-sharp-program-to-demonstrate-the-inheritance-of-abstract-classes/)

[抽象](https://www.geeksforgeeks.org/c-sharp-abstraction/)是隐藏内部细节，只显示功能的过程。抽象关键字用在类或方法之前，将类或方法声明为抽象的。[继承](https://www.geeksforgeeks.org/c-sharp-inheritance/)是面向对象的编程方法，通过这种方法，一个类可以继承另一个类的特性(字段和方法)。在 C# 中，我们还可以使用:运算符继承抽象类。

```cs
abstract class Abstract_class
{
    // Method declaration for abstract class
    public abstract void abstract_method();
}
class class_name  : Abstract_class
{
    // Method definition for abstract method
}
```

**进场:**

> *   Create an abstract class and declare a method in it using abstract keywords.
> *   Create a parent class by overriding the method of the abstract class.
> *   Create the first subclass of the inherited parent class and define a method in it.
> *   Create an object named "Geeks1 obj = new Geeks1 ()" for the first subclass in the main method.
> *   Call all methods declared using obj objects.

**示例:**

## C#

```cs
// C# program to inherit abstract class.
using System;

// Abstract class
abstract class Abstract_class
{

    // Method Declaration for abstract class
    public abstract void abstract_method();
}

// Parent class
class Geeks : Abstract_class
{

    // Method definition for abstract method
    public override void abstract_method()
    {
        Console.WriteLine("Abstract method is called");
    }
}

// First child class extends parent
class Geeks1 : Geeks
{

    // Method definition
    public void method1()
    {
        Console.WriteLine("method-1 is called");
    }
}

class GFG{

// Driver code
public static void Main(String[] args)
{

    // Create an object
    Geeks1 obj = new Geeks1();

    // Call the methods
    obj.abstract_method();
    obj.method1();
}
}
```

**输出:**

```cs
Abstract method is called
method-1 is called
```