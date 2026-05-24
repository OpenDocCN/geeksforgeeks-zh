# C# |类型。HasElementTypeImpl()方法

> 原文:[https://www . geesforgeks . org/c-sharp-type-haselementtypeimpl-method/](https://www.geeksforgeeks.org/c-sharp-type-haselementtypeimpl-method/)

**类型。HasElementTypeImpl()方法**在派生类中被重写时使用，实现 HasElementType 属性并确定当前类型是包含还是引用另一个类型。这意味着此方法检查当前类型是数组、指针还是通过引用传递的。

> **语法:**受保护的抽象 bool HasElementTypeImpl()；
> 
> **返回值:**如果类型是数组、指针或通过引用传递，则该方法返回 *true* ，否则返回 false。

以下程序说明了*类型的使用。HasElementTypeImpl()* 方法:

**例 1:**

```cs
// C# program to demonstrate the
// Type.HasElementTypeImpl() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating and initializing object of MyClass
        MyClass mytype = new MyClass(typeof(int));

        // checking if mytype has any elementtype or not
        if (mytype.HasElementType)
            Console.WriteLine("The type of myArray is {0}.", mytype.elementtype);
        else
            Console.WriteLine("myArray is not an array, pointer, or reference type.");
    }
}

// Defining MyClass extended from TypeDelegator
public class MyClass : TypeDelegator {

    // creating and initializing elementtype with null
    public string elementtype = null;

    // creating and initializing type with null
    private Type type = null;

    // Constructor
    public MyClass(Type type)
                 : base(type)
    {
        this.type = type;
    }

    // Override Type.HasElementTypeImpl().
    protected override bool HasElementTypeImpl()
    {

        // Determine whether the type is an array.
        if (type.IsArray) {
            elementtype = "array";
            return true;
        }

        // Determine whether the type is a reference.
        if (type.IsByRef) 
        {
            elementtype = "reference";
            return true;
        }

        // Determine whether the type is a pointer.
        if (type.IsPointer)
        {
            elementtype = "pointer";
            return true;
        }

        // Return false if the type is not
        // a reference, array, or pointer type.
        return false;
    }
}
```

**Output:**

```cs
myArray is not an array, pointer, or reference type.

```

**例 2:**

```cs
// C# program to demonstrate the
// Type.HasElementTypeImpl() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating and initializing object of MyClass
        MyClass mytype = new MyClass(typeof(int[,,,,,, ]));

        // checking if mytype has any elementtype or not
        if (mytype.HasElementType)
            Console.WriteLine("The type of {1} is {0}.",
                       mytype.elementtype, mytype.type);
        else
            Console.WriteLine("{0} is not an array, pointer, or reference type.",
                                                                    mytype.type);
    }
}

// Defining MyClass extended from TypeDelegator
public class MyClass : TypeDelegator {

    // creating and initializing elementtype with null
    public string elementtype = null;

    // creating and initializing type with null
    public Type type = null;

    // Constructor
    public MyClass(Type type)
                : base(type)
    {
        this.type = type;
    }

    // Override Type.HasElementTypeImpl().
    protected override bool HasElementTypeImpl()
    {
        // Determine whether the type is an array.
        if (type.IsArray) 
        {

            elementtype = "array";
            return true;
        }

        // Determine whether the type is a reference.
        if (type.IsByRef) 
        {
            elementtype = "reference";
            return true;
        }

        // Determine whether the type is a pointer.
        if (type.IsPointer) 
        {
            elementtype = "pointer";
            return true;
        }

        // Return false if the type is not a 
        // reference, array, or a pointer type
        return false;
    }
}
```

**Output:**

```cs
The type of System.Int32[,,,,,,] is array.

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . haselementtypeimpl？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.haselementtypeimpl?view=netframework-4.8)