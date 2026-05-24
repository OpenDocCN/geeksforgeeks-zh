# C# |构造函数

> 原文:[https://www.geeksforgeeks.org/c-sharp-constructors/](https://www.geeksforgeeks.org/c-sharp-constructors/)

构造函数是该类的一种特殊方法，每当创建该类的实例时都会自动调用该方法。与方法一样，构造函数也包含在对象创建时执行的指令集合。用于为同一类的**数据成员**分配初始值。

**示例:**

```cs
class Geek
{   
  .......
  // Constructor
  public Geek() {}
  .......
}

// an object is created of Geek class,
// So above constructor is called
Geek obj = new Geek(); 

```

### 关于构造函数需要记住的要点

*   类的构造函数必须与其所在的类名同名。
*   构造函数不能是抽象的、最终的和同步的。
*   在一个类中，只能创建一个静态构造函数。
*   构造函数没有任何返回类型，甚至没有 void。
*   静态构造函数不能是参数化构造函数。
*   一个类可以有任意数量的构造函数。
*   在构造函数声明中可以使用访问修饰符来控制它的访问，即哪个类可以调用构造函数。

### 构造函数的类型

1.  **默认构造函数**
2.  **参数化构造器**
3.  **复制构造器**
4.  **私人建造商**
5.  **静态构造器**

### 默认构造函数

没有参数的构造函数称为默认构造函数。默认构造函数将类的每个实例初始化为相同的值。默认构造函数将类中的所有数值字段初始化为零，并将所有字符串和对象字段初始化为空。

**示例:**

## C#

```cs
// C# Program to illustrate calling
// a Default constructor
using System;
namespace DefaultConstructorExample {

class Geek {

    int num;
    string name;

    // this would be invoked while the
    // object of that class created.
    Geek()
    {
        Console.WriteLine("Constructor Called");
    }

    // Main Method
    public static void Main()
    {

        // this would invoke default
        // constructor.
        Geek geek1 = new Geek();

        // Default constructor provides
        // the default values to the
        // int and object as 0, null
        // Note:
        // It Give Warning because
        // Fields are not assign
        Console.WriteLine(geek1.name);
        Console.WriteLine(geek1.num);
    }
}
}
```

**输出:**

```cs
Constructor Called

0

```

**注意:**这也会显示如下一些警告:

```cs
prog.cs(8, 6): warning CS0649: Field `DefaultConstructorExample.Geek.num' is never assigned to, and will always have its default value `0'
prog.cs(9, 9): warning CS0649: Field `DefaultConstructorExample.Geek.name' is never assigned to, and will always have its default value `null'

```

### 参数化构造函数

至少有一个参数的构造函数称为参数化构造函数。它可以将类的每个实例初始化为不同的值。

**示例:**

## C#

```cs
// C# Program to illustrate calling of
// parameterized constructor.
using System;
namespace ParameterizedConstructorExample {

class Geek {

    // data members of the class.
    String name;
    int id;

    // parameterized constructor would
    // initialized data members with
    // the values of passed arguments
    // while object of that class created.
    Geek(String name, int id)
    {
        this.name = name;
        this.id = id;
    }

    // Main Method
    public static void Main()
    {

        // This will invoke parameterized
        // constructor.
        Geek geek1 = new Geek("GFG", 1);
        Console.WriteLine("GeekName = " + geek1.name +
                         " and GeekId = " + geek1.id);
    }
}
}
```

**输出:**

```cs
GeekName = GFG and GeekId = 1 

```

### 复制构造函数

此构造函数通过从另一个对象复制变量来创建一个对象。它的主要用途是将新实例初始化为现有实例的值。

**示例:**

## C#

```cs
// C# Program to illustrate calling
// a Copy constructor
using System;
namespace copyConstructorExample {

class Geeks {

    private string month;
    private int year;

    // declaring Copy constructor
    public Geeks(Geeks s)
    {
        month = s.month;
        year = s.year;
    }

    // Instance constructor
    public Geeks(string month, int year)
    {
        this.month = month;
        this.year = year;
    }

    // Get details of Geeks
    public string Details
    {
        get
        {
            return "Month: " + month.ToString() +
                     "\nYear: " + year.ToString();
        }
    }

    // Main Method
    public static void Main()
    {

        // Create a new Geeks object.
        Geeks g1 = new Geeks("June", 2018);

        // here is g1 details is copied to g2.
        Geeks g2 = new Geeks(g1);

        Console.WriteLine(g2.Details);
    }
}
}
```

**输出:**

```cs
Month: June
Year: 2018

```

### 私有构造函数

如果构造函数是用私有说明符创建的，则称为私有构造函数。其他类不可能从这个类派生，也不可能创建这个类的实例。

**需要记住的要点:**

*   它是单例类模式的实现。
*   当我们只有静态成员时，使用私有构造函数。
*   使用私有构造函数，可以防止创建该类的实例。

**示例:**

## C#

```cs
// C# Program to illustrate calling
// a Private constructor
using System;
namespace privateConstructorExample {

public class Geeks {

    // declare private Constructor
    private Geeks()
    {
    }

    // declare static variable field
    public static int count_geeks;

    // declare static method
    public static int geeks_Count()
    {
        return ++count_geeks;
    }

    // Main Method
    public static void Main()
    {

        // If you uncomment the following
        // statement, it will generate
        // an error because the constructor
        // is unaccessible:
        // Geeks s = new Geeks(); // Error

        Geeks.count_geeks = 99;

        // Accessing without any
        // instance of the class
        Geeks.geeks_Count();

        Console.WriteLine(Geeks.count_geeks);

        // Accessing without any
        // instance of the class
        Geeks.geeks_Count();

        Console.WriteLine(Geeks.count_geeks);
    }
}
}
```

**输出:**

```cs
100
101

```

### 静态构造函数

静态构造函数在类中只能被调用一次，并且在创建对类中静态成员的第一个引用时被调用。静态构造函数是类的初始化静态字段或数据，只执行一次。

**需要记住的要点:**

*   不能直接调用。
*   当它执行时，用户没有控制权。
*   它不接受访问修饰符或任何参数。
*   在创建第一个实例之前，会自动调用它来初始化类。

**示例:**

## C#

```cs
// C# Program to illustrate calling
// a Static constructor
using System;
namespace staticConstructorExample {

class geeks {

    // It is invoked before the first
    // instance constructor is run.
    static geeks()
    {

        // The following statement produces
        // the first line of output,
        // and the line occurs only once.
        Console.WriteLine("Static Constructor");
    }

    // Instance constructor.
    public geeks(int i)
    {
        Console.WriteLine("Instance Constructor " + i);
    }

    // Instance method.
    public string geeks_detail(string name, int id)
    {
        return "Name:" + name + " id:" + id;
    }

    // Main Method
    public static void Main()
    {

        // Here Both Static and instance
        // constructors are invoked for
        // first instance
        geeks obj = new geeks(1);

        Console.WriteLine(obj.geeks_detail("GFG", 1));

        // Here only instance constructor
        // will be invoked
        geeks obj1 = new geeks(2);

        Console.WriteLine(obj1.geeks_detail("GeeksforGeeks", 2));
    }
}
}
```

**输出:**

```cs
Static Constructor
Instance Constructor 1
Name:GFG id:1
Instance Constructor 2
Name:GeeksforGeeks id:2

```