# C# |变量类型

> 原文:[https://www.geeksforgeeks.org/c-sharp-types-of-variables/](https://www.geeksforgeeks.org/c-sharp-types-of-variables/)

一个[变量](https://www.geeksforgeeks.org/c-variables/)是一个内存位置的名称，对该变量所做的所有操作都会影响该内存位置。在 [C# ](https://www.geeksforgeeks.org/introduction-to-c-sharp/) 中，所有的变量都必须声明后才能使用。它是程序中的基本存储单元。存储在变量中的值可以在程序执行过程中更改。

### 变量的类型

*   局部变量
*   实例变量或非静态变量
*   静态变量或类变量
*   常量变量
*   只读变量

### 局部变量

在块、方法或构造函数中定义的变量称为局部变量。

*   这些变量是在进入程序块或函数在退出程序块后被调用和销毁时，或函数返回调用时创建的。
*   这些变量的作用域只存在于声明该变量的块中。也就是说，我们只能在该块内访问这些变量。

**例 1:**

## C#

```cs
// C# program to demonstrate
// the local variables
using System;
class StudentDetails {

    // Method
    public void StudentAge()
    {

        // local variable age
        int age = 0;

        age = age + 10;
        Console.WriteLine("Student age is : " + age);
    }

    // Main Method
    public static void Main(String[] args)
    {

        // Creating object
        StudentDetails obj = new StudentDetails();

        // calling the function
        obj.StudentAge();
    }
}
```

**输出:**

```cs
Student age is : 10
```

**说明:**在上面的程序中，变量“age”是函数 StudentAge()的局部变量。如果我们使用 StudentAge()函数之外的变量 age，编译器会产生如下程序所示的错误。

**例 2:**

## C#

```cs
// C# program to demonstrate the error
// due to using the local variable
// outside its scope
using System;

class StudentDetails {

    // Method
    public void StudentAge()
    {

        // local variable age
        int age = 0;
        age = age + 10;
    }

    // Main Method
    public static void Main(String[] args)
    {

        // using local variable age outside it's scope
        Console.WriteLine("Student age is : " + age);
    }
}
```

**错误:**

> prog.cs(22，43):错误 CS0103:名称` age '在当前上下文中不存在

### 实例变量或非静态变量

实例变量是非静态变量，在类中声明，但在任何方法、构造函数或块之外。由于实例变量是在类中声明的，因此这些变量是在类的对象创建时创建的，而在对象销毁时销毁。与局部变量不同，我们可以对实例变量使用访问说明符。

**示例:**

## C#

```cs
// C# program to illustrate the
// Instance variables
using System;

class Marks {

    // These variables are instance variables.
    // These variables are in a class and
    // are not inside any function
    int engMarks;
    int mathsMarks;
    int phyMarks;

    // Main Method
    public static void Main(String[] args)
    {

        // first object
        Marks obj1 = new Marks();
        obj1.engMarks = 90;
        obj1.mathsMarks = 80;
        obj1.phyMarks = 93;

        // second object
        Marks obj2 = new Marks();
        obj2.engMarks = 95;
        obj2.mathsMarks = 70;
        obj2.phyMarks = 90;

        // displaying marks for first object
        Console.WriteLine("Marks for first object:");
        Console.WriteLine(obj1.engMarks);
        Console.WriteLine(obj1.mathsMarks);
        Console.WriteLine(obj1.phyMarks);

        // displaying marks for second object
        Console.WriteLine("Marks for second object:");
        Console.WriteLine(obj2.engMarks);
        Console.WriteLine(obj2.mathsMarks);
        Console.WriteLine(obj2.phyMarks);
    }
}
```

**输出:**

```cs
Marks for first object:
90
80
93
Marks for second object:
95
70
90
```

**说明:**在上面的程序中，变量 engMarks、mathsMarks、phymarks 都是实例变量。如果像上面的程序一样有多个对象，那么每个对象都有自己的实例变量副本。从上面的输出可以清楚地看到，每个对象都有自己的实例变量副本。

### 静态变量或类变量

静态变量也称为类变量。如果变量是用静态修饰符显式声明的，或者如果变量是在任何静态块下声明的，那么这些变量被称为静态变量。

*   这些变量被类似地声明为实例变量，区别在于静态变量是在任何方法构造函数或块之外的类中使用 static 关键字声明的。
*   与实例变量不同，不管我们创建多少对象，每个类只能有一个静态变量的副本。
*   静态变量在程序执行开始时创建，在执行结束时自动销毁。

**注意:**要访问静态变量，不需要创建该类的任何对象，只需访问变量如下:

```cs
class_name.variable_name;
```

**示例:**

## C#

```cs
// C# program to illustrate
// the static variables
using System;
class Emp {

    // static variable salary
    static double salary;
    static String name = "Aks";

    // Main Method
    public static void Main(String[] args)
    {

        // accessing static variable
        // without object
        Emp.salary = 100000;

        Console.WriteLine(Emp.name + "'s average salary:"
                                           + Emp.salary);
    }
}
```

**输出:**

```cs
Aks's average salary:100000
```

**注意:**非静态变量的初始化与实例创建和构造函数调用相关联，因此非静态变量也可以通过构造函数进行初始化。我们不通过构造函数初始化静态变量，因为每次构造函数调用时，它都会用新值覆盖现有值。

### 实例变量和静态变量之间的区别

*   每个对象都有自己的实例变量副本，而不管我们创建多少个对象，每个类只能有一个静态变量副本。
*   使用一个对象在实例变量中所做的更改不会反映在其他对象中，因为每个对象都有自己的实例变量副本。在静态的情况下，变化将反映在其他对象中，因为静态变量是一个类的所有对象所共有的。
*   我们可以通过对象引用来访问实例变量，静态变量可以使用类名直接访问。
*   在一个类的生命周期中，静态变量只初始化一次，而实例变量在没有创建实例的情况下初始化 0 次，在创建了 n 个实例的情况下初始化 n 次。
*   静态变量和实例变量的语法如下:

```cs
 class Example
        {
            static int a; // static variable
            int b;        // instance variable
        }

```

### 常量变量

如果一个变量是用关键字“ **const** 声明的，那么它就是一个常量变量，这些常量变量在声明后不能修改一次，所以它必须只在声明时初始化。

**例 1:** 由于常量变量声明时没有提供值，下面的程序会显示错误。

## C#

```cs
// C# program to illustrate the
// constant variables
using System;
class Program {

    // constant variable max
    // but no value is provided
    const float max;

    // Main Method
    public static void Main()
    {

        // creating object
        Program obj = new Program();

        // it will give  error
        Console.WriteLine("The value of b is = " + Program.b);
    }
}
```

**错误:**

> prog.cs(8，17):错误 CS0145:常量字段需要提供一个值

**示例 2:** 显示常量变量使用的程序

## C#

```cs
// C# program to illustrate the
// constant variable
using System;
class Program {

    // instance variable
    int a = 10;

    // static variable
    static int b = 20;

    // constant variable
    const float max = 50;

    // Main Method
    public static void Main()
    {

        // creating object
        Program obj = new Program();

        // displaying result
        Console.WriteLine("The value of a is = " + obj.a);
        Console.WriteLine("The value of b is = " + Program.b);
        Console.WriteLine("The value of max is = " + Program.max);
    }
}
```

**输出:**

```cs
The value of a is = 10
The value of b is = 20
The value of max is = 50
```

**关于常量变量的要点:**

*   常量变量的**行为将类似于静态变量**的行为，即在一个类的生命周期中初始化一次且只初始化一次，不需要该类的实例进行访问或初始化。
*   静态变量和常量变量的区别在于，静态变量可以修改，而常量变量一旦声明就不能修改。

### 只读变量

如果使用 **readonly 关键字**声明一个变量，那么它将是只读变量，并且这些变量不能像常量一样修改，但是在初始化之后。

*   在声明时初始化只读变量并不是强制性的，它们也可以在构造函数下初始化。
*   只读变量的行为将类似于非静态变量的行为，即仅在创建类的实例之后初始化，并且对于创建的类的每个实例初始化一次。

**示例 1:** 在下面的程序中，只读变量 k 没有用任何值初始化，但是当我们打印变量的值时，默认值 int 即 0 将显示如下:

## C#

```cs
// C# program to show the use
// of readonly variables
// without initializing it
using System;
class Program {

    // instance variable
    int a = 80;

    // static variable
    static int b = 40;

    // Constant variables
    const float max = 50;

    // readonly variables
    readonly int k;

    // Main Method
    public static void Main()
    {

        // Creating object
        Program obj = new Program();

        Console.WriteLine("The value of a is = " + obj.a);
        Console.WriteLine("The value of b is = " + Program.b);
        Console.WriteLine("The value of max is = " + Program.max);
        Console.WriteLine("The value of k is = " + obj.k);
    }
}
```

**输出:**

```cs
The value of a is = 80
The value of b is = 40
The value of max is = 50
The value of k is = 0
```

**示例 2:** 显示构造函数中只读变量的初始化。

## C#

```cs
// C# program to illustrate the
// initialization of readonly
// variables in the constructor
using System;
class Geeks {

    // instance variable
    int a = 80;

    // static variable
    static int b = 40;

    // Constant variables
    const float max = 50;

    // readonly variables
    readonly int k;

    // constructor
    public Geeks()
    {

        // initializing readonly
        // variable k
        this.k = 90;
    }

    // Main Method
    public static void Main()
    {

        // Creating object
        Geeks obj = new Geeks();

        Console.WriteLine("The value of a is = " + obj.a);
        Console.WriteLine("The value of b is = " + Geeks.b);
        Console.WriteLine("The value of max is = " + Geeks.max);
        Console.WriteLine("The value of k is = " + obj.k);
    }
}
```

**输出:**

```cs
The value of a is = 80
The value of b is = 40
The value of max is = 50
The value of k is = 90
```

**示例 3:** 演示只读变量在其声明和外部构造函数之后初始化的程序:

## C#

```cs
// C# program to illustrate the
// initialization of readonly
// variables twice
using System;
class Geeks {

    // instance variable
    int a = 80;

    // static variable
    static int b = 40;

    // Constant variables
    const float max = 50;

    // readonly variables
    readonly int k;

    // constructor
    public Geeks()
    {

        // first time initializing
        // readonly variable k
        this.k = 90;
    }

    // Main Method
    public static void Main()
    {

        // Creating object
        Geeks obj = new Geeks();

        Console.WriteLine("The value of a is = " + obj.a);
        Console.WriteLine("The value of b is = " + Geeks.b);
        Console.WriteLine("The value of max is = " + Geeks.max);

        // initializing readonly variable again
        // will compile time error
        obj.k = 55;

        Console.WriteLine("The value of k is = " + obj.k);
    }
}
```

**错误:**

> prog.cs(41，13):错误 CS0191:只读字段“Geeks.k”不能赋值给(构造函数或变量初始值设定项中除外)

**关于只读变量的要点:**

*   只读和实例变量唯一的区别**是实例变量可以修改，只读变量不能修改。**
*   常量变量是整个类的固定值，而只读变量是特定于类实例的固定值。