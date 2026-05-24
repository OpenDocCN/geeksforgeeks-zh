# C # 8.0 中的默认接口方法

> 原文:[https://www . geesforgeks . org/default-interface-methods-in-c-sharp-8-0/](https://www.geeksforgeeks.org/default-interface-methods-in-c-sharp-8-0/)

在 C# 8.0 [之前，接口](https://www.geeksforgeeks.org/c-sharp-interface/)只包含成员(方法、属性、事件和索引器)的声明，但是从 C# 8.0 开始，允许向接口添加成员及其实现。现在，您可以在不破坏接口的现有实现的情况下向接口添加一个带有实现的方法，这种类型的方法被称为**默认接口方法(也称为虚拟扩展方法)**。这个特性允许程序员使用特征编程技术(特征是面向对象的编程技术，允许在不相关的类之间重用方法)。

**要点:**

*   您可以在接口中实现索引器、属性或事件访问器。
*   您可以使用访问修饰符，如私有、受保护、内部、公共、虚拟、抽象、覆盖、密封、静态、带有默认方法的外部等。在界面上。并且在使用修饰语关键字时要小心。
*   您可以在接口中创建静态字段、方法、属性、索引器和事件。
*   您可以覆盖修改器。
*   默认访问的显式访问修饰符是公共的。
*   如果接口包含默认方法并由某个指定的类继承，则该类不知道该接口的默认方法的存在，也不包含默认方法的实现。
*   如果覆盖默认方法，那么就不需要使用任何修饰符。如例 2 所示。
*   您可以在默认方法中使用参数。如例 3 所示。
*   您可以在接口中使用相同名称的方法，但是它们必须有不同的参数列表。如例 3 所示。
*   您可以扩展默认方法。

现在借助给定的例子讨论这个概念。在这个例子中，我们有一个名为 *I_interface* 的界面，它包含两种方法，即 *display_1* 和 *display_2* 。这里 *display_1()* 方法只在 *I_interface* 中声明，不包含其定义，而 *display_2()* 方法既包含声明又包含其定义，这种类型的方法称为默认接口方法。

**例 1:**

```cs
// C# program to illustrate the concept
// of the default interface method
using System;

// A simple interface
interface I_interface {

    // This method is only
    // have its declaration
    // not its definition
    void display_1();

    // Default method with both 
    // declaration and definition
    public void display_2()
    {
        Console.WriteLine("Hello!! Default Method");
    }
}

// A class that implements
// the I_interface interface.
class Example_Class : I_interface {

    // Providing the body
    // part of the method
    public void display_1()
    {
        Console.WriteLine("Hello!! Method");
    }

    // Main Method
    public static void Main(String[] args)
    {

        // Creating an object
        Example_Class t = new Example_Class();

        // Calling method
        t.display_1();

        // Creating an object
        I_interface obj = t;

        // Calling default method
        obj.display_2();
    }
}
```

**输出:**

```cs
Hello!! Method
Hello!! Default Method

```

现在，我们借助 *I_interface* 界面调用 *display_2()* 方法。如果试图用类对象调用此方法

```cs
// Calling default method
// With the help of Example_Class object
t.display_2();

```

那么编译器会给出如下所示的错误:

> 错误 CS1061:“Example_Class”不包含“display_2”的定义，并且找不到接受“Example _ Class”类型的第一个参数的可访问扩展方法“display_2”(是否缺少 using 指令或程序集引用？)

**例 2:**

```cs
// C# program to illustrate how to override
// the default interface method
using System;

// A simple interface
interface I_interface {

    // This method having
    // only declaration
    // not its definition
    void display_1();

    // Default method has both 
    // declaration and definition
    public void display_2()
    {
        Console.WriteLine("Hello!!  Default Method of I_interface");
    }
}

// Interface which inherits I_interface
interface A_interface : I_interface {

    // Here, we override the display_2() method
    // Here you are not allowed to use any access modifier
    // if you use, then the compiler will give an error
    void I_interface.display_2()
    {
        Console.WriteLine("Hello!! Overriden default method");
    }
}

// A class that implements both interfaces.
class Example_Class : I_interface, A_interface {

    // Providing the body part of the method
    public void display_1()
    {
        Console.WriteLine("Hello!! Method of I_interface");
    }

    // Main Method
    public static void Main(String[] args)
    {

        // Creating object
        Example_Class t = new Example_Class();

        // Calling method
        t.display_1();

        // Creating an object
        I_interface obj1 = t;

        // Calling default method
        obj1.display_2();

        // Creating an object
        A_interface obj2 = t;
        obj2.display_2();
    }
}
```

**输出:**

```cs
Hello!! Method of I_interface
Hello!! Overriden default method
Hello!! Overriden default method

```

**例 3:**

```cs
// C# program to illustrate how 
// to pass parameters in the
// default interface method
using System;

// A simple interface
interface I_interface {

    // This method only
    // have declaration
    // not its definition
    void display_1();

    // Default method with both
    // declaration and definition
    // Here, the name of both methods are same
    // but the parameter list is different
    public void display_1(int a, int b)
    {
        int sum;
        sum = a + b;
        Console.WriteLine("Sum: " + sum);
    }
}

// A class which 
// implement I_interface interface
class Example_Class : I_interface {

    // Providing the body
    // part of the method
    public void display_1()
    {
        Console.WriteLine("Hello!! Method of I_interface");
    }

    // Main Method
    public static void Main(String[] args)
    {

        // Creating an object
        Example_Class t = new Example_Class();

        // Calling method
        t.display_1();

        // Creating an object
        I_interface obj = t;

        // Calling and passing parameters in the default method
        obj.display_1(1, 4);
    }
}
```

**输出:**

```cs
Hello!! Method of I_interface
Sum: 5

```