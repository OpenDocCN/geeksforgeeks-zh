# C# 程序继承同一个类中的抽象类和接口

> 原文：[https://www.geeksforgeeks.org/c-sharp-program-to-inherit-an-abstract-class-and-interface-in-the-same-class/](https://www.geeksforgeeks.org/c-sharp-program-to-inherit-an-abstract-class-and-interface-in-the-same-class/)

## 抽象类

`抽象类`是实现抽象的方式。它是一个特殊的类，永远不会被直接实例化。这个类应该至少包含一个抽象方法，并在类定义中用`abstract`关键字标记。这个类的主要目的是为派生类提供一个蓝图，并设置一些规则，当派生类继承一个抽象类时必须实现这些规则。抽象类可以用作基类，所有派生类都必须实现抽象定义。

**语法** :

```cs
abstract class classname
{
    // Method Declaration in abstract class
}
```

这里，`classname`是抽象类的名称。我们可以在其中声明任意数量的方法。

## 接口

`接口`就像一个类，它也可以有方法、属性、事件和索引器作为它的成员。但是接口只能有成员的声明。接口成员的实现将由隐式或显式实现接口的类给出。或者我们可以说它是班级的蓝图。

**语法**:

```cs
interface interface_name
{
    // Method Declaration in interface
}
```

## 方法

现在给定一个接口和一个抽象类，现在我们的任务是继承同一个类中的接口和抽象类。

*   使用`abstract`关键字创建一个抽象类，并为抽象方法编写方法定义。
*   使用`interface`关键字创建一个接口，并为接口编写方法定义。
*   创建一个名为`GFG`的类，它将继承抽象类和接口，如下所示：

```cs
class GFG : Abstract_Class, Interface
{
    // Method definition for abstract method
    // Method definition for interface
}
```

*   在`GFG`类中为抽象类和接口编写方法定义。
*   在`Main`方法中，为抽象类和接口创建两个对象。
*   使用这些对象调用方法并显示输出。

## 例

### c\#

```cs
// C# program to illustrate how to inherit an
// abstract class and interface in the same class
using System;

// Abstract class
abstract class Abstract_Class
{

// Method declaration in abstract class
    public abstract void abstract_method();
}

// Interface
interface Interface
{

// Method declaration in interface
    void interface_method();
}

// Here, GFg class inherit abstract class and interface
class GFG : Abstract_Class, Interface
{

// Method definition for abstract method
    public override void abstract_method()
    {
        Console.WriteLine("I am the method of abstract class");
    }

// Method definition for interface
    public void interface_method()
    {
        Console.WriteLine("I am the method of interface");
    }
}

class Geeks{

// Driver code
public static void Main(String[] args)
{

// Creating objects
    Abstract_Class ac = new GFG();
    Interface inf = new GFG();

// Calling the methods of abstract class
    // and interface
    ac.abstract_method();
    inf.interface_method();
}
}
```

**输出** :

```cs
I am the method of abstract class
I am the method of interface
```