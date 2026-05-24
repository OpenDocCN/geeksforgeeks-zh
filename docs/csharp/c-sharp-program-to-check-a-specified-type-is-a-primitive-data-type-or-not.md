# 检查指定类型是否为原始数据类型的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-check-a-specified-type-is-a-primitive-data-type-or-not/](https://www.geeksforgeeks.org/c-sharp-program-to-check-a-specified-type-is-a-primitive-data-type-or-not/)

在 C# 中，数据类型用于指定变量可以容纳的数据类型。C# 中有两种类型的数据类型，即基元数据类型和非基元数据类型。基本数据类型是预定义的数据类型，如字节、字节、布尔、Int16、UInt16、Int32、UInt32、Char、Double、Int64、UInt64、Single 等。而非原语数据类型是用户定义的数据类型，如枚举、类等。在本文中，我们将学习如何检查指定的类型是否是原始数据类型。因此，为了完成这个任务，我们使用类型类的**是主要属性**。此属性用于检查指定数据的类型是否是基元类型之一。如果给定的数据类型是原语，则返回 true，否则返回 false。

**语法:**

```cs
public bool IsPrimitive{ get; }
```

**例**:

## C#

```cs
// C# program to check a specified type 
// is a primitive data type or not
using System;
using System.Reflection;

class GFG{

static void Main()
{

    // Check the int is an primitiva or not
    if (typeof(int).IsPrimitive == true)
    {
        Console.WriteLine("Primitive data type");
    }
    else 
    {
        Console.WriteLine("Not a primitive data type");
    }

    // Check the float is an primitiva or not
    if (typeof(float).IsPrimitive == true) 
    {
        Console.WriteLine("Primitive data type");
    }
    else 
    {
        Console.WriteLine("Not a primitive data type");
    }

    // Check the int is an primitiva or not
    if (typeof(double).IsPrimitive == true) 
    {
        Console.WriteLine("Primitive data type");
    }
    else 
    {
        Console.WriteLine("Not a primitive data type");
    }
}
}
```

**输出:**

```cs
Primitive data type
Primitive data type
Primitive data type
```