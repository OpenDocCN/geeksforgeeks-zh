# 如何在 C# 中创建 2 值元组？

> 原文：[https://www.geeksforgeeks.org/how-to-create-2-valuetuple-in-c-sharp/](https://www.geeksforgeeks.org/how-to-create-2-valuetuple-in-c-sharp/)

在 C# 中，一对或两个值的元组是包含两个元素的值类型元组。您可以使用两种不同的方法创建一对值元组：

1.  使用 `ValueTuple<T1, T2>(T1, T2)` 构造函数
2.  使用 `Create<T1, T2>(T1, T2)` 方法

## 使用 `ValueTuple<T1, T2>(T1, T2)` 构造函数

您可以使用 `ValueTuple<T1, T2>(T1, T2)` 构造函数创建一个对值元组。它初始化了 `ValueTuple<T1, T2>` 结构的一个新实例。但是当您使用这个构造函数创建一个值元组时，您必须指定存储在值元组中的元素的类型。

**语法：**

```cs
public ValueTuple (T1 item1, T2 item2);
```

**参数：**

*   `item1`：是第一个值元组组件的值。
*   `item2`：是第二个值元组组件的值。

**示例：**

```cs
// C# program to create a pair ValueTuple
// using value tuple constructor
using System;

class GFG {

// Main method
    static public void Main()
    {

// Creating a value tuple with two elements
        // Using ValueTuple<T1, T2>(T1, T2) constructor
        ValueTuple<string, string> MyTpl = new ValueTuple<string, 
                                 string>("Geeks", "GFG");

Console.WriteLine("Component 1: " + MyTpl.Item1);
        Console.WriteLine("Component 2: " + MyTpl.Item2);
    }
}
```

**Output：**

```cs
Component 1: Geeks
Component 2: GFG
```

## 使用 `Create<T1, T2>(T1, T2)` 方法

您也可以借助 `Create<T1, T2>(T1, T2)` 方法创建一个对值元组。当您使用此方法时，就不需要指定存储在值元组中的元素的类型。

**语法：**

```cs
public static ValueTuple<T1, T2> Create<T1, T2> (T1 item1, T2 item2);
```

**类型参数：**

*   `T1`：它是值元组的第一个组件的类型。
*   `T2`：它是值元组的第二个组成部分的类型。

**参数：**

*   `item1`：它是值元组的第一个分量的值。
*   `item2`：它是值元组的第二个分量的值。

**返回：** 这个方法返回一个包含两个元素的值元组。

**示例：**

```cs
// C# program to create a pair value tuple
// using Create<T1, T2>(T1, T2) method
using System;

public class GFG {

// Main method
    static public void Main()
    {

// Creating a value tuple with two elements
        // Using Create<T1, T2>(T1, T2) method
        var MyTple = ValueTuple.Create("Geeks123", "gfg");

Console.WriteLine("Component 1: " + MyTple.Item1);
        Console.WriteLine("Component 2: " + MyTple.Item2);
    }
}
```

**Output：**

```cs
Component 1: Geeks123
Component 2: gfg
```

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple-2.-ctor?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple-2.-ctor?view=netframework-4.8)
*   [https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple.create?view=netframework-4.8#System_ValueTuple_Create__2___0___1_](https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple.create?view=netframework-4.8#System_ValueTuple_Create__2___0___1_)