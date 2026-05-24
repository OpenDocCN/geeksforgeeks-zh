# C# Type.IsArrayImpl() 方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-type-isarrayimpl-method/](https://www.geeksforgeeks.org/c-sharp-type-isarrayimpl-method/)

`Type.IsArrayImpl()` 方法在派生类中被重写时使用，用于实现 `IsArray` 属性并确定类型是否为数组。

## 语法
```cs
protected abstract bool IsArrayImpl();
```

## 返回值
如果类型为数组，该方法返回 `true`，否则返回 `false`。

以下程序说明了 `Type.IsArrayImpl()` 方法的使用：

## 示例 1
```cs
// C# program to demonstrate the
// Type.IsArrayImpl() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating and initializing object of MyClass
        MyClass mytype = new MyClass(typeof(int));

        // checking if mytype has any
        // elementtype or not
        if (mytype.HasElementType)
            Console.WriteLine("The type of myArray is {0}.",
                                mytype.elementtype);
        else
            Console.WriteLine("myArray is not an array, pointer,"+
                               "or reference type.");
    }
}

// Defining MyClass extended from TypeDelegator
public class MyClass : TypeDelegator {

    // creating and initializing
    // elementtype with null
    public string elementtype = null;

    // creating and initializing 
    // type with null
    private Type type = null;

    // Constructor
    public MyClass(Type type)
                : base(type)
    {
        this.type = type;
    }

    // Override Type.IsArrayImpl().
    protected override bool IsArrayImpl()
    {
        // Determine whether the type is an array.
        if (type.IsArray) 
        {
            elementtype = "array";
            return true;
        }
        // Return false if the type is not
        // a reference, array, or pointer type.
        return false;
    }
}
```

**输出:**
```cs
myArray is not an array, pointer,or reference type.
```

## 示例 2
```cs
// C# program to demonstrate the
// Type.IsArrayImpl() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating and initializing object of MyClass
        MyClass mytype = new MyClass(typeof(int[,,,, ]));

        // checking if mytype has
        // any elementtype or not
        if (mytype.HasElementType)
            Console.WriteLine("The type of {0} is array.",
                                mytype.type);
        else
            Console.WriteLine("myArray is not an array,"+
                      "pointer, or reference type.");
    }
}

// Defining MyClass extended from TypeDelegator
public class MyClass : TypeDelegator {

    // creating and initializing
    // elementtype with null
    public string elementtype = null;

    // creating and initializing 
    // type with null
    public Type type = null;

    // Constructor
    public MyClass(Type type)
                 : base(type)
    {
        this.type = type;
    }

    // Override Type.IsArrayImpl().
    protected override bool IsArrayImpl()
    {

        // Determine whether the
        // type is an array.
        if (type.IsArray)
        {
            elementtype = "array";
            return true;
        }

        // Return false if the type is not
        // a reference, array, or pointer type.
        return false;
    }
}
```

**输出:**
```cs
The type of System.Int32[,,,,] is array.
```

## 参考
* [https://docs.microsoft.com/en-us/dotnet/api/system.type.isarrayimpl?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.isarrayimpl?view=netframework-4.8)