# 如何在 C# 中创建 1 元组或单元组？

> 原文：[https://www.geeksforgeeks.org/how-to-create-1-tuple-or-singleton-tuple-in-c-sharp/](https://www.geeksforgeeks.org/how-to-create-1-tuple-or-singleton-tuple-in-c-sharp/)

在 C# 中，单元组是只包含一个元素的[元组](https://www.geeksforgeeks.org/c-sharp-tuple/)，单元组也被称为 **1 元组**。您可以使用两种不同的方法创建 1 元组：

*   使用 `Tuple<T1>(T1)` 构造器
*   使用 `Create` 方法

## 使用 `Tuple<T1>(T1)` 构造器

您可以使用 `Tuple<T1>(T1)` 构造函数创建单元组。它初始化 `Tuple<T1>` 类的一个新实例。但是当你使用这个构造函数创建一个元组时，那么你必须指定存储在元组中的元素的类型。

**语法：**

```cs
public Tuple (T1 item1);
```

这里，`item1` 是元组唯一组成部分的值。

**示例：**

```cs
// C# program to create singleton 
// tuple using tuple constructor
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Creating tuple with one elements
        // Using Tuple<T1>(T1) constructor
        Tuple<string> My_Tuple = new Tuple<string>("GeeksforGeeks");

        Console.WriteLine("Element: " + My_Tuple.Item1);
    }
}
```

**输出：**

```cs
Element: GeeksforGeeks
```

## 使用 `Create` 方法

您也可以在 `Create` 方法的帮助下创建一个单元组。当你使用这个方法时，那么就不需要指定存储在元组中的元素的类型。

**语法：**

```cs
public static Tuple<T1> Create<T1> (T1 item1);
```

这里，`item1` 是元组元素的值，`T1` 是存储在元组中的元素的类型。

**返回类型：** 该方法返回单元组的组件，其值为 `item1`。

**示例：**

```cs
// C# program to create 1-tuple
// using create method
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Creating tuple with one elements
        // Using Create method
        var My_Tuple = Tuple.Create("Geeks");

        Console.WriteLine("Element: " + My_Tuple.Item1);
    }
}
```

**输出：**

```cs
Element: Geeks
```

**参考文献：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.tuple-1.-ctor?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.tuple-1.-ctor?view=netframework-4.8)
*   [https://docs.microsoft.com/en-us/dotnet/api/system.tuple.create?view=netframework-4.8#System_Tuple_Create__1___0_](https://docs.microsoft.com/en-us/dotnet/api/system.tuple.create?view=netframework-4.8#System_Tuple_Create__1___0_)