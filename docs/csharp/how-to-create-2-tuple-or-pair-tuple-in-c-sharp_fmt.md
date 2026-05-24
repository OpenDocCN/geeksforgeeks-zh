# 如何在 C# 中创建 2 元组或对元组？

> 原文：[https://www.geeksforgeeks.org/how-to-create-2-tuple-or-pair-tuple-in-c-sharp/](https://www.geeksforgeeks.org/how-to-create-2-tuple-or-pair-tuple-in-c-sharp/)

在 C# 中，2 元组是包含两个元素的[元组](https://www.geeksforgeeks.org/c-sharp-tuple/)，也称为**对**。您可以使用两种不同的方法创建二元组：

*   [使用 `Tuple<T1, T2>(T1, T2)` 构造器](#使用-tuplet1-t2t1-t2-构造器)
*   [使用 `Create` 方法](#使用-create-方法)

## 使用 `Tuple<T1, T2>(T1, T2)` 构造器

您可以使用 `Tuple<T1, T2>(T1, T2)` 构造函数创建 2 元组。它初始化 `Tuple` 类的一个新实例。但是当你使用这个构造函数创建一个元组时，那么*你必须指定存储在元组中的元素*的类型。

**语法：**

```cs
public Tuple (T1 item1, T2 item2);
```

**参数：**

*   `item1`：是第一个元组成分的值。
*   `item2`：是第二元组分量的值。

**示例：**

```cs
// C# program to create 2-tuple
// using the tuple constructor
using System;

public class GFG {

    // Main method
    static public void Main()
    {
        // Creating tuple with two elements
        // Using Tuple<P1, P2>(T1, T2) constructor
        Tuple<string, int> My_Tuple = new Tuple<string, int>("GeeksforGeeks", 10);

        Console.WriteLine("Element 1: " + My_Tuple.Item1);
        Console.WriteLine("Element 2: " + My_Tuple.Item2);
    }
}
```

**输出：**

```cs
Element 1: GeeksforGeeks
Element 2: 10
```

## 使用 `Create` 方法

您也可以在 `Create` 方法的帮助下创建二元组。当你使用这个方法时，那么*就不需要指定存储在元组中的元素的类型*。

**语法：**

```cs
public static Tuple<T1,T2> Create<T1, T2> (T1 item1, T2 item2);
```

**类型参数：**

*   `T1`：是第一个元组成分的类型。
*   `T2`：是第二元组成分的类型。

**参数：**

*   `item1`：是第一个元组成分的值。
*   `item2`：是第二元组分量的值。

**返回类型：** 该方法返回 2 元组，其值为 `item1` 和 `item2`。

**示例：**

```cs
// C# program to create 2-tuple
// using create method
using System;

public class GFG {

    // Main method
    static public void Main()
    {
        // Creating tuple with two elements
        // Using Create method
        var My_Tuple = Tuple.Create("Geeks", 20);

        Console.WriteLine("Element 1: " + My_Tuple.Item1);
        Console.WriteLine("Element 2: " + My_Tuple.Item2);
    }
}
```

**输出：**

```cs
Element 1: Geeks
Element 2: 20
```

**参考文献：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.tuple-2.-ctor?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.tuple-2.-ctor?view=netframework-4.8)
*   [https://docs.microsoft.com/en-us/dotnet/api/system.tuple.create?view=netframework-4.8#System_Tuple_Create__2___0___1_](https://docs.microsoft.com/en-us/dotnet/api/system.tuple.create?view=netframework-4.8#System_Tuple_Create__2___0___1_)