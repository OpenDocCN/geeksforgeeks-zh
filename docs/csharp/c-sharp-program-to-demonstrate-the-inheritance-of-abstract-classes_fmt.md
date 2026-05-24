# 演示抽象类继承的 C# 程序

> 原文：[https://www.geeksforgeeks.org/c-sharp-program-to-demonstrate-the-inheritance-of-abstract-classes/](https://www.geeksforgeeks.org/c-sharp-program-to-demonstrate-the-inheritance-of-abstract-classes/)

[抽象](https://www.geeksforgeeks.org/c-sharp-abstraction/)是隐藏内部细节，只显示功能的过程。`abstract`关键字用在类或方法之前，将类或方法声明为抽象的。[继承](https://www.geeksforgeeks.org/c-sharp-inheritance/)是面向对象的编程方法，通过这种方法，一个类可以继承另一个类的特性（字段和方法）。在 C# 中，我们还可以使用 `:` 运算符继承抽象类。

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

## 进场：

-   创建一个抽象类，并使用 `abstract` 关键字在其中声明一个方法。
-   通过重写抽象类的方法来创建一个父类。
-   创建继承父类的第一个子类，并在其中定义一个方法。
-   在主方法中为第一个子类创建一个名为 `Geeks1 obj = new Geeks1()` 的对象。
-   使用 `obj` 对象调用所有声明的方法。

## 示例：

### C\#

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

## 输出：

```cs
Abstract method is called
method-1 is called
```