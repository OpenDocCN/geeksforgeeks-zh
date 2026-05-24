# C# `Type.IsAssignableFrom(Type)` 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-type-isassignablefromtype-method/](https://www.geeksforgeeks.org/c-sharp-type-isassignablefromtype-method/)

## 方法描述
`Type.IsAssignableFrom(Type)` 方法用于确定指定类型的实例是否可以分配给当前类型的变量。

## 语法
```cs
public virtual bool IsAssignableFrom(Type c);
```
这里是拿类型 `c` 和当前的类型比较。

## 返回值
如果下列任一条件为真，则该方法返回 `true`：
*   `c` 和当前实例表示相同的类型。
*   `c` 直接或间接从当前实例派生。如果 `c` 从当前实例继承，则直接从当前实例派生；如果 `c` 从继承自当前实例的一个或多个类的继承中继承，则它从当前实例间接派生。
*   当前实例是 `c` 实现的接口。
*   `c` 是泛型类型参数，当前实例表示 `c` 的一个约束。

## 示例
以下程序说明了 `Type.IsAssignableFrom()` 方法的使用：

### 例 1
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
**输出：**
```cs
Instance of a specified type can be assigned to a variable of the current type.
```

### 例 2
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
**输出：**
```cs
Instance of a specified type can't be assigned to a variable of the current type.
```

## 参考
*   [https://docs.microsoft.com/en-us/dotnet/api/system.type.isassignablefrom?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.isassignablefrom?view=netframework-4.8)