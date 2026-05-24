# C# |类型。IsAssignableFrom(类型)方法

> 原文:[https://www . geesforgeks . org/c-sharp-type-isassignablefromtype-method/](https://www.geeksforgeeks.org/c-sharp-type-isassignablefromtype-method/)

**类型。IsAssignableFrom(类型)方法**用于确定指定类型的实例是否可以分配给当前类型的变量。

> **语法:**公共虚拟 bool IsAssignableFrom(Type c)；
> 这里是拿类型和现在的类型比较。
> 
> **返回值:**如果下列任一条件为真，则该方法返回真:
> 
> *   c 和当前实例表示相同的类型。
> *   c 直接或间接从当前实例派生。如果 c 从当前实例继承，则直接从当前实例派生；如果 c 从继承自当前实例的一个或多个类的继承中继承，则它从当前实例间接派生。
> *   当前实例是 c 实现的接口。
> *   c 是泛型类型参数，当前实例表示 c 的一个约束。

以下程序说明了*类型的使用。IsAssignableFrom()* 方法:

**例 1:**

```cs
// C# program to demonstrate the
// Type.IsAssignableFrom() Method
using System;
using System.Globalization;
using System.Reflection;
using System.IO;

// Defining MyClass extended
// from TypeDelegator
public class MyClass : TypeDelegator { }

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing object of Type
        Type objType = typeof(TypeDelegator);

        // Getting array of Properties by
        // using GetProperties() Method
        bool status = objType.IsAssignableFrom(typeof(MyClass));

        // Display the Result
        if (status)
            Console.WriteLine("Instance of a specified type can be "
                   + "assigned to a variable of the current type.");
        else
            Console.WriteLine("Instance of a specified type can't be "
                     + "assigned to a variable of the current type.");
    }
}
```

**Output:**

```cs
Instance of a specified type can be assigned to a variable of the current type.

```

**例 2:**

```cs
// C# program to demonstrate the
// Type.IsAssignableFrom() Method
using System;
using System.Globalization;
using System.Reflection;
using System.IO;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing object of Type
        Type objType = typeof(double);

        // Getting array of Properties by
        // using GetProperties() Method
        bool status = objType.IsAssignableFrom(typeof(int));

        // Display the Result
        if (status)
            Console.WriteLine("Instance of a specified type can be "
                   + "assigned to a variable of the current type.");
        else
            Console.WriteLine("Instance of a specified type can't be "
                     + "assigned to a variable of the current type.");
    }
}
```

**Output:**

```cs
Instance of a specified type can't be assigned to a variable of the current type.

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . isassignablefrom？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.isassignablefrom?view=netframework-4.8)