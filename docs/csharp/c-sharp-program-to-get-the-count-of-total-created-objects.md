# C# 程序获取创建对象总数

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-get-count-total-created-objects/](https://www.geeksforgeeks.org/c-sharp-program-to-get-the-count-of-total-created-objects/)

C# 是一种通用编程语言，用于创建移动应用程序、桌面应用程序、网站和游戏。在 C# 中，对象是真实世界的实体。或者换句话说，对象是在运行时创建的运行时实体。它是一个类的实例。在本文中，我们将创建一个类的多个实例或对象，并计算在 C# 中创建的对象的数量。

**进场:**

> *   Create a class named DemoClass, and we are creating several objects for it.
> *   We use the main method to create a class (GetCount), from which we will create several objects of DemoClass.
> *   In Democlass, we will define a static variable count and initialize it to 0.
> *   Create a constructor for DemoClass, which increments the count every time an object of DemoClass is created.
> *   We define it as static here, because a single copy of a variable is created and shared among all objects at the class level, so whenever we create a new object, the value of count will not be lost.
> *   Create a static method (TotalCount) to return the count value. The static method is a method called on the class itself, not a method called on the object.
> *   Create multiple objects of DemoClass in the main method, and call the TotalCount method with the class name (DemoClass).

**例 1:**

## C#

```cs
// C# program to illustrate the above concept
using System;

class DemoClass{

// The static variable count is used to store
// the count of objects created.
static int count = 0;

// Constructor of the class, in which count
// value will be incremented
public DemoClass() 
{ 
    count++; 
}

// Method totalcount is used to return 
// the count variable.
public static int TotalCount() 
{  
    return count; 
}
}

class GFG{

static void Main(string[] args)
{

    // Printing the number of objects before 
    // creating objects.
    Console.WriteLine("Total objects = " + 
                      DemoClass.TotalCount());

    // Creating the objects of DemoClass
    DemoClass C1 = new DemoClass();
    DemoClass C2 = new DemoClass();
    DemoClass C3 = new DemoClass();

    // Printing the number of objects after 
    // creating 3 objects.
    Console.WriteLine("Total objects = " + 
                      DemoClass.TotalCount());
}
}
```

**输出:**

```cs
Total objects = 0
Total objects = 3
```

**例 2:**

## C#

```cs
// C# program to illustrate the above concept
using System;

class DemoClass{

// Here, the static variable count is used to 
// store the count of objects created.
static int count = 0;

// constructor of the class, in which 
// count value will be incremented
public DemoClass() 
{ 
    count++; 
}

// Method totalcount is used to return
// the count variable.
public static int TotalCount() 
{ 
    return count; 
}
}

class GFG{

static void Main(string[] args)
{

    // Printing the number of objects before
    // creating objects.
    Console.WriteLine("Total objects = " + 
                      DemoClass.TotalCount());

    // Creating the objects of DemoClass
    DemoClass C1 = new DemoClass();
    DemoClass C2 = new DemoClass();
    DemoClass C3 = new DemoClass();
    DemoClass C4 = new DemoClass();
    DemoClass C5 = new DemoClass();
    DemoClass C6 = new DemoClass();

    // Printing the number of objects after 
    // creating 3 objects.
    Console.WriteLine("Total objects = " + 
                      DemoClass.TotalCount());
}
}
```

**输出:**

```cs
Total objects = 0
Total objects = 6
```