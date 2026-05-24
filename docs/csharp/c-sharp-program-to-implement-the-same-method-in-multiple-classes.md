# 在多个类中实现相同方法的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-多类实现同一个方法的程序/](https://www.geeksforgeeks.org/c-sharp-program-to-implement-the-same-method-in-multiple-classes/)

C# 是一种通用编程语言，用于创建移动应用程序、桌面应用程序、网站和游戏。在 C# 中，对象是真实世界的实体。或者换句话说，对象是在运行时创建的运行时实体。它是一个类的实例。在本文中，在多个类中实现相同的方法在多个类中实现相同的方法可以通过使用[接口](https://www.geeksforgeeks.org/c-sharp-interface/)来实现。接口就像类一样，它也有方法、属性、索引器和事件。但它只包含成员的声明，其成员的实现将由隐式或显式实现接口的类给出。或者我们可以说所有在接口内部声明的方法都是抽象方法。用来实现类无法实现的多重继承。

**进场:**

> *   Create an interface and declare a method (that is, greet)
> *   Now create three classes named Class1, Class2 and Class3, and define the method greet () in all classes.
> *   Create the class DemoClass and define the main methods.
> *   In the Main method, create a reference variable for the Interface, initialize the reference variable through the objects of class1, class2 and class3, and then call the method greet ().

**例 1:**

## C#

```cs
// C# program to illustrate the above concept
using System;

interface Interface
{

    // Declaring Method
    void greet();
}

// Creating classes and define the method 
// greet() in all classes.
class Class1 : Interface
{
    public void greet()
    {
        Console.WriteLine("Welcome Geeks");
    }    
}

class Class2 : Interface
{
    public void greet()
    {
        Console.WriteLine("Hello Geeks");
    }    
}

class Class3 : Interface
{
    public void greet()
    {
        Console.WriteLine("Bella Ciao Geeks");
    }    
}

class GFG{

public static void Main(String[] args)
{

    // I is the reference variable of Interface
    Interface I;

    // Initializing the I with objects of all the
    // classes one by one and calling the method greet()
    I = new Class1();
    I.greet();

    I = new Class2();
    I.greet();

    I = new Class3();
    I.greet();
}
}
```

**Output**

```cs
Welcome Geeks
Hello Geeks
Bella Ciao Geeks
```

**例 2:**

## C#

```cs
// C# program to illustrate the above concept
using System;

// Interface
interface Interface
{

    // Declaring Method 
    void greet();
}

// Creating classes and define the method
// greet() in all classes.
class Class1 : Interface
{
    public void greet()
    {
        Console.WriteLine("Welcome Geeks");
    }    
}

class Class2 : Interface
{
    public void greet()
    {
        Console.WriteLine("Hello Geeks");
    }    
}

class Class3 : Interface
{
    public void greet()
    {
        Console.WriteLine("Bella Ciao Geeks");
    }    
}

class Class4 : Interface
{
    public void greet()
    {
        Console.WriteLine("hola geeks");
    }    
}

class Class5 : Interface
{
    public void greet()
    {
        Console.WriteLine("welcome to geeksforgeeks");
    }
}

class GFG{

public static void Main(String[] args)
{

    // I is the reference variable of Interface
    Interface I;

    // Initializing the I with objects of all the
    // classes one by one and calling the method greet()
    I = new Class1();
    I.greet();

    I = new Class2();
    I.greet();

    I = new Class3();
    I.greet();

    I = new Class4();
    I.greet();

    I = new Class5();
    I.greet();
}
}
```

**Output**

```cs
Welcome Geeks
Hello Geeks
Bella Ciao Geeks
hola geeks
welcome to geeksforgeeks
```