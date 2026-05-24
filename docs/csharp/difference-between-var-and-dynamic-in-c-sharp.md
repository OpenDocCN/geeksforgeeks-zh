# c# 中 var 和动态的区别

> 原文:[https://www . geeksforgeeks . org/var 和动态 in-c-sharp 的区别/](https://www.geeksforgeeks.org/difference-between-var-and-dynamic-in-c-sharp/)

**[隐式类型化局部变量–var](https://www.geeksforgeeks.org/c-sharp-implicitly-typed-local-variables-var/)**是那些在没有指定*的情况下声明的变量。NET 类型*显式。在隐式类型变量中，变量的类型由编译器在编译时从用于初始化变量的值中自动推导出来。在 **C# 3.0** 中引入了隐式类型变量的概念。隐式类型化变量不是用来代替普通变量声明的，它是用来处理一些特殊情况的，比如 *LINQ* (语言集成查询)。

**示例:**

```cs
// C# program to illustrate the concept
// of the implicitly typed variable
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating and initializing
        // implicitly typed variables
        // Using var keyword
        var a = 'f';
        var b = "GeeksforGeeks";
        var c = 30.67d;
        var d = false;
        var e = 54544;

        // Display the type
        Console.WriteLine("Type of 'a' is : {0} ", a.GetType());

        Console.WriteLine("Type of 'b' is : {0} ", b.GetType());

        Console.WriteLine("Type of 'c' is : {0} ", c.GetType());

        Console.WriteLine("Type of 'd' is : {0} ", d.GetType());

        Console.WriteLine("Type of 'e' is : {0} ", e.GetType());
    }
}
```

**输出:**

```cs
Type of 'a' is : System.Char 
Type of 'b' is : System.String 
Type of 'c' is : System.Double 
Type of 'd' is : System.Boolean 
Type of 'e' is : System.Int32 

```

在 **C# 4.0** 中，引入了一种新的类型，称为**动态类型**。它用于避免编译时类型检查。编译器不会在编译时检查动态类型变量的类型，而是在运行时获取类型。动态类型变量是使用动态关键字创建的。

**示例:**

```cs
// C# program to illustrate how to get the
// actual type of the dynamic type variable
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Dynamic variables
        dynamic val1 = "GeeksforGeeks";
        dynamic val2 = 3234;
        dynamic val3 = 32.55;
        dynamic val4 = true;

        // Get the actual type of
        // dynamic variables
        // Using GetType() method
        Console.WriteLine("Get the actual type of val1: {0}",
                                  val1.GetType().ToString());

        Console.WriteLine("Get the actual type of val2: {0}",
                                  val2.GetType().ToString());

        Console.WriteLine("Get the actual type of val3: {0}",
                                  val3.GetType().ToString());

        Console.WriteLine("Get the actual type of val4: {0}",
                                  val4.GetType().ToString());
    }
}
```

**输出:**

```cs
Get the actual type of val1: System.String
Get the actual type of val2: System.Int32
Get the actual type of val3: System.Double
Get the actual type of val4: System.Boolean

```

下面是 C# 中 var 和动态关键字的一些区别:

| 定义变量 | 动态的 |
| 它是在 C# 3.0 中引入的。 | 它是在 C# 4.0 中引入的 |
| 使用 var 关键字声明的变量是静态类型的。 | 使用动态关键字声明的变量是动态类型的。 |
| 变量的类型由编译器在编译时决定。 | 变量的类型由编译器在运行时决定。 |
| 这种类型的变量应该在声明时初始化。这样编译器将根据它初始化的值来决定变量的类型。 | 这种类型的变量不需要在声明时初始化。因为编译器在编译时不知道变量的类型。 |
| 如果变量没有初始化，它会抛出一个错误。 | 如果变量没有初始化，它不会抛出错误。 |
| 它支持 visual studio 中的智能感知。 | 它不支持 visual studio 中的智能感知 |
| var myvalue = 10//语句 1
my value = " geeks forgeeks "；//语句 2
这里编译器会抛出一个错误，因为编译器已经使用整数类型的语句 1 决定了 myvalue 变量的类型。当您试图将字符串赋给 myvalue 变量时，编译器会给出一个错误，因为它违反了安全规则类型。 | 动态 myvalue = 10//语句 1
my value = " geeks forgeeks "；//语句 2
这里，虽然 myvalue 的类型是整数，但是编译器不会抛出错误。当您将一个字符串赋给 myvalue 时，它会重新创建 myvalue 的类型，并毫无错误地接受该字符串。 |
| 它不能用于属性或从函数返回值。它只能用作函数中的局部变量。 | 它可以用于属性或从函数返回值。 |