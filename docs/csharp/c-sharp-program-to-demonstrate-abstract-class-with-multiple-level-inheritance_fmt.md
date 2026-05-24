# 演示多级继承抽象类的 C# 程序

> 原文：[https://www.geeksforgeeks.org/c-sharp-program-to-demonstrate-abstract-class-with-multiple-level-inheritance/](https://www.geeksforgeeks.org/c-sharp-program-to-demonstrate-abstract-class-with-multiple-level-inheritance/)

`抽象类`是实现抽象的方式。它是一个特殊的类，永远不会被直接实例化。这个类应该至少包含一个抽象方法，并在类定义中用`abstract`关键字标记。这个类的主要目的是为派生类提供一个蓝图，并设置一些规则，当派生类继承一个抽象类时必须实现这些规则。抽象类可以用作基类，所有派生类都必须实现抽象定义。

**语法**：

```cs
abstract class classname
{
    // Method Declaration in abstract class
}
```

这里，`classname`是抽象类的名称。我们可以在其中声明任意数量的方法。

`多级继承`是一种继承类型，其中一个派生类将继承一个基类，并且该派生类对于其他类也表现得像基类一样。例如，我们有三个名为`Class1`、`Class2`和`Class3`的类。这里，`Class3`源自`Class2`，`Class2`源自`Class1`。

**语法**：

```cs
class GFG : Abstract_Class
{
    // Method definition for abstract method
}
```

### 抽象类的多级继承

给定一个抽象类，我们的任务是将抽象类实现到父类中，然后实现多级继承。所以，让我们借助一个例子来理解。

```cs
class GFG : Abstract_class
{
   // Method definition for abstract method
}

// First child class extends parent
class GFG2 : GFG
{
    // Method definition
}

// Second child class extends first child class
class GFG3 : GFG2
{
    // Method definition
}
```

这里，`GFG`是父类，`GFG2`和`GFG3`是扩展父类的子类。

**例**：

## c#

```cs
// C# program to illustrate abstract class 
// with multiple-level Inheritance
using System;

// Abstract class
abstract class Abstract_class
{

// Method declaration for abstract class
    public abstract void abstract_method();
}

// Parent class
class GFG : Abstract_class
{

// Method definition for abstract method
    public override void abstract_method()
    {
        Console.WriteLine("Abstract method is called");
    }
}

// First child class extends parent
class GFG2 : GFG
{

// Method definition
    public void Mymethod1()
    {
        Console.WriteLine("Method from GFG2 class");
    }
}

// Second child class extends first child class
class GFG3 : GFG2
{

// Method definition
    public void Mymethod2()
    {
        Console.WriteLine("Method from GFG3 class");
    }
}

class Geeks{

// Driver code
public static void Main(String[] args)
{

// Creating an object of GFG3 class
    GFG3 obj = new GFG3();

// Call the methods using GFG3 class
    obj.abstract_method();
    obj.Mymethod1();
    obj.Mymethod2();
}
}
```

**输出**：

```cs
Abstract method is called
Method from GFG2 class
Method from GFG3 class
```

**说明**：在这个例子中，我们创建了一个名为`Abstract_class`的抽象类，并在其中声明了一个名为`abstract_method()`的方法。然后，我们通过重写抽象类的方法创建了一个名为`GFG`的父类。之后，我们创建了第一个名为`GFG2`的子类，它继承了父类，并在其中定义了一个名为`Mymethod1()`的方法。然后创建了名为`GFG3`的第二个子类，它继承了第一个子类，并在其中定义了一个方法`Mymethod2()`。最后，我们创建了包含`Main(String[] args)`方法的`Geeks`类，然后为第二子类创建了一个对象（名为`obj`），并调用了所有声明的方法，并在屏幕上获得了输出。