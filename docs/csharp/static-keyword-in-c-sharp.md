# c# 中的静态关键字

> 原文:[https://www.geeksforgeeks.org/static-keyword-in-c-sharp/](https://www.geeksforgeeks.org/static-keyword-in-c-sharp/)

**static** 是 C# 中的修饰符，适用于以下情况:

*   [级](https://www.geeksforgeeks.org/c-sharp-class-and-object/)
*   [variable](https://www.geeksforgeeks.org/c-sharp-variables/)
*   [Method](https://www.geeksforgeeks.org/c-sharp-methods/)
*   [constructor](https://www.geeksforgeeks.org/c-sharp-constructors/)

也适用于 [*属性*](https://www.geeksforgeeks.org/c-properties/) 、事件、 [*操作符*](https://www.geeksforgeeks.org/c-operators/) 。要创建一个静态成员(类、变量、方法、构造函数)，在它的声明前面加上关键字 *static* 。当一个成员被声明为静态时，可以用它的类名直接访问它。

#### 静态类

借助 *static* 关键字声明一个静态类。静态类只能包含静态数据成员、静态方法和静态构造函数。不允许创建静态类的对象。静态类是 [***封***](https://www.geeksforgeeks.org/c-sealed-class/) ，意味着一个静态类不能从另一个类继承。

**例:**

## c#

```cs
// C# program to illustrate the
// concept of a static class
using System;

// Creating static class
// Using static keyword
static class Tutorial {

    // Static data members of Tutorial
    public static string Topic = "Static class";
}

// Driver Class
public class GFG {

    // Main Method
    static public void Main()
    {

        // Accessing the static data members of Tutorial
        Console.WriteLine("Topic name is : {0} ", Tutorial.Topic);
    }
}
```

**输出:**

```cs
Topic name is : Static class 
```

#### 静态变量

静态变量是在 static 关键字的帮助下声明的。当一个变量被声明为静态变量时，就会创建该变量的一个副本，并在类级别的所有对象之间共享。静态变量是用类名来访问的，它们不需要任何对象来访问。

**例:**

## c#

```cs
// C# program to illustrate the
// concept of static variable
using System;

class Vehicle {

    // Creating static variable
    // Using static keyword
    public static string Model_color = "Black";
}

// Driver Class
public class GFG {

    // Main Method
    static public void Main()
    {

        // Accessing the static variable
        // using its class name
        Console.WriteLine("Color of XY model is  : {0} ",
                                    Vehicle.Model_color);
    }
}
```

**输出:**

```cs
Color of XY model is  : Black 
```

#### 静态法

静态方法是借助 static 关键字声明的。静态方法是用类名访问的。静态方法可以访问静态和非静态字段，静态字段由静态方法直接访问，没有类名，而非静态字段需要对象。

**例:**

## c#

```cs
// C# program to illustrate the
// concept of static method
using System;

class Nparks {

    static public int t = 104;

    // Creating static method
    // Using static keyword
    public static void total()
    {
        Console.WriteLine("Total number of national parks"+
                           " present in India is :{0}", t);
    }
}

// Driver Class
public class GFG {

    // Main Method
    static public void Main()
    {

        // Accessing the static method
        // using its class name
        Nparks.total();
    }
}
```

**输出:**

```cs
Total number of national parks present in India is :104
```

#### 静态构造函数

静态构造函数是在 static 关键字的帮助下声明的。静态构造函数在类中只能被调用一次，并且在创建对类中静态成员的第一个引用时被调用。静态构造函数是类的初始化静态字段或数据，只执行一次。

**要记住的点:**

*   You can't scream directly.
*   When it is executing, then the user has no control.
*   Without access modifiers or any parameters.
*   Automatically call the initialization class before creating the first instance.

**例:**

## c#

```cs
// C# Program to illustrate calling
// a Static constructor
using System;

class G1 {

    // It is invoked before the first
    // instance constructor is run.
    static G1()
    {

        // The following statement produces
        // the first line of output,
        // and the line occurs only once.
        Console.WriteLine("Example of Static Constructor");
    }

    // Instance constructor.
    public G1(int j)
    {
        Console.WriteLine("Instance Constructor " + j);
    }

    // Instance method.
    public string g1_detail(string name, string branch)
    {
        return "Name: " + name + " Branch: " + branch;
    }

    // Main Method
    public static void Main()
    {

        // Here Both Static and instance
        // constructors are invoked for
        // first instance
        G1 obj = new G1(1);

        Console.WriteLine(obj.g1_detail("Sunil", "CSE"));

        // Here only instance constructor
        // will be invoked
        G1 ob = new G1(2);

        Console.WriteLine(ob.g1_detail("Sweta", "ECE"));
    }
}
```

**输出:**

```cs
Example of Static Constructor
Instance Constructor 1
Name: Sunil Branch: CSE
Instance Constructor 2
Name: Sweta Branch: ECE
```

**使用静态关键字的限制:**

*   Static keywords cannot be used by types other than [indexer](https://www.geeksforgeeks.org/c-indexers/) , finalizer or class.
*   Static members are not referenced by instances.
*   In C#, this is not allowed to refer to static methods or property accessors.
*   In C#, if the static keyword is used with the class, the static class always contains static members.