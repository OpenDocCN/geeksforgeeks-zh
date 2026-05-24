# C# 程序获取创建对象总数

> 原文：[https://www.geeksforgeeks.org/c-sharp-program-to-get-the-count-of-total-created-objects/](https://www.geeksforgeeks.org/c-sharp-program-to-get-the-count-of-total-created-objects/)

C# 是一种通用编程语言，用于创建移动应用程序、桌面应用程序、网站和游戏。在 C# 中，对象是真实世界的实体。或者换句话说，对象是在运行时创建的运行时实体。它是一个类的实例。在本文中，我们将创建一个类的多个实例或对象，并计算在 C# 中创建的对象的数量。

**方法：**

*   创建一个名为 `DemoClass` 的类，并为其创建多个对象。
*   我们使用 `Main` 方法来创建一个类（`GetCount`），从中我们将创建 `DemoClass` 的多个对象。
*   在 `DemoClass` 中，我们将定义一个静态变量 `count` 并将其初始化为 0。
*   为 `DemoClass` 创建一个构造函数，该函数在每次创建 `DemoClass` 的对象时递增 `count`。
*   我们在这里将其定义为 `static`，因为变量的单个副本是在类级别创建并在所有对象之间共享的，因此每当我们创建新对象时，`count` 的值都不会丢失。
*   创建一个静态方法（`TotalCount`）来返回 `count` 值。静态方法是在类本身上调用的方法，而不是在对象上调用的方法。
*   在 `Main` 方法中创建 `DemoClass` 的多个对象，并使用类名（`DemoClass`）调用 `TotalCount` 方法。

## 例 1

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

**输出：**

```cs
Total objects = 0
Total objects = 3
```

## 例 2

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

**输出：**

```cs
Total objects = 0
Total objects = 6
```