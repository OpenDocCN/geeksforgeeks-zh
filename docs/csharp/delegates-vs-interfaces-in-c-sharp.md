# c# 中的委托与接口

> 原文:[https://www . geesforgeks . org/delegates-vs-interfaces-in-c-sharp/](https://www.geeksforgeeks.org/delegates-vs-interfaces-in-c-sharp/)

一个 [**委托**](https://www.geeksforgeeks.org/c-sharp-delegates/) 是一个引用方法的对象，或者你可以说它是一个引用类型变量，可以保存对方法的引用。C# 中的委托类似于 C/C++ 中的[函数指针。它提供了一种方法，告诉在事件被触发时调用哪个方法。](https://www.geeksforgeeks.org/function-pointer-in-c/)

**示例:**

```cs
// C# program to illustrate Delegates
using System;

class GFG {

    // Declaring the delegates
    public delegate void AddVal(int x, int y);

    public void SMeth(int x, int y)
    {
        Console.WriteLine("[190 + 70] = [{0}]", x + y);
    }

    // Main Method
    public static void Main(String[] args)
    {

        // Creating the object of GFG class
        GFG o = new GFG();

        // Creating object of delegate
        AddVal obj = new AddVal(o.SMeth);

        // Pass the values to the method
        // Using delegate object
        obj(190, 70);
    }
}
```

**输出:**

```cs
[190 + 70] = [260]

```

像类一样， **[接口](https://www.geeksforgeeks.org/c-sharp-interface/)** 可以有方法、属性、事件和索引器作为其成员。但是接口将只包含成员的声明。接口成员的实现将由隐式或显式实现接口的类给出。

**示例:**

```cs
// C# program to illustrate the
// concept of interface
using System;

// A simple interface
interface inter {

    // method having only declaration
    // not definition
    void display();
}

// A class that implements the interface
class Geeks : inter {

    // providing the body part of function
    public void display()
    {
        Console.WriteLine("Welcome to GeeksforGeeks..!");
    }

    // Main Method
    public static void Main(String[] args)
    {

        // Creating object
        Geeks o = new Geeks();

        // calling method
        o.display();
    }
}
```

**输出:**

```cs
Welcome to GeeksforGeeks..!

```

**下面是 C# 中委托和接口的一些区别:**

| **委托** | **界面** |
| --- | --- |
| 这可能只是一种方法。 | 它包含方法和属性。 |
| 它可以一次应用于一种方法。 | 如果一个类实现了一个接口，那么它将实现与该接口相关的所有方法。 |
| 如果委托在您的范围内可用，您可以使用它。 | 接口在类实现该接口时使用，否则不使用。 |
| 委托可以实现任何次数。 | 接口只能实现一次。 |
| 它用于处理事件。 | 它不用于处理事件。 |
| 它可以访问匿名方法。 | 它不能访问匿名方法。 |
| 当使用委托访问方法时，不需要对定义方法的类的对象进行任何访问。 | 当您访问方法时，您需要实现接口的类的对象。 |
| 它不支持继承。 | 它支持继承。 |
| 它可以包装静态方法和密封类方法 | 它不包装静态方法和密封类方法.. |
| 它在运行时创建。 | 它是在编译时创建的。 |
| 它可以实现为给定委托提供相同签名的任何方法。 | 如果实现了接口的方法，那么相同的名称和签名方法将被覆盖。 |
| 它可以包装任何签名与委托相似的方法，并且不考虑它属于哪个类。 | 一个类可以实现任意数量的接口，但是只能重写那些属于接口的方法。 |