# C# Type.GetInterfaces() 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-type-getinterfaces-method/](https://www.geeksforgeeks.org/c-sharp-type-getinterfaces-method/)

`Type.GetInterfaces()` 方法用于在派生类中被重写时，获取当前类型实现或继承的所有接口。

> **语法：**
> `public abstract Type[] GetInterfaces();`
>
> **返回值：**
> 该方法返回一个 `Type` 对象数组，表示当前类型实现或继承的所有接口。如果当前类型没有实现或继承任何接口，则返回 `Type` 的空数组。

以下程序说明了 `Type.GetInterfaces()` 方法的使用：

## 例 1

```cs
// C# program to demonstrate the
// Type.GetInterfaces() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing object of Type
        Type objType = typeof(int);

        // Getting interface of specified name
        // using GetField(String) Method
        Type[] minterface = objType.GetInterfaces();

        // Display the Result
        Console.WriteLine("Interface present in type {0}", objType);
        for (int i = 0; i < minterface.Length; i++)
            Console.WriteLine(" {0}", minterface[i]);
    }
}
```

**输出：**

```cs
Interface present in type System.Int32
 System.IFormattable
 System.IComparable
 System.IComparable`1[System.Int32]
 System.IConvertible
 System.IEquatable`1[System.Int32]
```