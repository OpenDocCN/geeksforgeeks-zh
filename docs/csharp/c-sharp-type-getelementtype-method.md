# C# |类型。GetElementType()方法

> 原文:[https://www . geesforgeks . org/c-sharp-type-getelementtype-method/](https://www.geeksforgeeks.org/c-sharp-type-getelementtype-method/)

**类型。GetElementType()方法**用于在派生类中被重写时返回当前数组、指针或引用类型包含或引用的对象的类型。

> **语法:**公共抽象类型 GetElementType()；
> 
> **返回值:**此方法返回当前数组、指针或引用类型包含或引用的对象的类型，如果当前类型不是数组或指针，或者不是通过引用传递的，或者表示泛型类型或泛型方法定义中的泛型类型或类型参数，则返回 null。

以下程序说明了*类型的使用。GetElementType()* 方法:

**例 1:**

```cs
// C# program to demonstrate the
// Type.GetElementType() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing type
        Type type = typeof(int[,, ]);

        // using GetElementType() Method
        Type t = type.GetElementType();

        // Display the ElementType
        Console.WriteLine("ElementType is: {0}", t);
    }
}
```

**Output:**

```cs
ElementType is: System.Int32

```

**例 2:**

```cs
// C# program to demonstrate the
// Type.GetElementType() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {
        // Creating the object of class
        GFG obj = new GFG();

        Type typ1 = obj.GetType();
        Type typ2 = typ1.GetElementType();

        Console.WriteLine("Element type of {0} is {1}", obj, 
                      typ2==null? "null" : typ2.ToString());
    }

}
```

**Output:**

```cs
Element type of GFG is null

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . getelementtype？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.getelementtype?view=netframework-4.8)