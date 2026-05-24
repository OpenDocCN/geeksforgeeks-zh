# 如何在 C# 中创建 4 元组或四元组？

> 原文：[https://www.geeksforgeeks.org/how-to-create-4-tuple-or-quadruple-in-c-sharp/](https://www.geeksforgeeks.org/how-to-create-4-tuple-or-quadruple-in-c-sharp/)

在 C# 中，4 元组是包含 4 个元素的[元组](https://www.geeksforgeeks.org/c-sharp-tuple/)，也称为四元组。您可以使用两种不同的方法创建一个 4 元组：

*   使用 `Tuple<T1,T2,T3,T4>(T1, T2, T3, T4)` 构造器
*   使用 `Create` 方法

## 使用 `Tuple<T1,T2,T3,T4>(T1, T2, T3, T4)` 构造器

可以使用 `Tuple<T1,T2,T3,T4>(T1, T2, T3, T4)` 构造器创建 4 元组。它初始化 `Tuple<T1,T2,T3,T4>` 类的一个新实例。但是当你使用这个构造函数创建一个元组时，那么你必须指定存储在元组中的元素的类型。

### 语法

```cs
public Tuple (T1 item1, T2 item2, T3 item3, T4 item4);
```

### 参数

*   `item1`：是第一个元组成分的值。
*   `item2`：是第二元组分量的值。
*   `item3`：是第三元组分量的值。
*   `item4`：是第四元组分量的值。

### 示例

```cs
// C# program to create 4-tuple
// using the tuple constructor
using System;

public class GFG {

// Main method
    static public void Main()
    {

// Creating tuple with four elements
        // Using Tuple<T1, T2, T3, T4>(T1, 
        // T2, T3, t4) constructor
        Tuple<string, int, char, double> My_Tuple = new Tuple<string,
                  int, char, double>("GeeksforGeeks", 10, 'G', 20.4);

        Console.WriteLine("Element 1: " + My_Tuple.Item1);
        Console.WriteLine("Element 2: " + My_Tuple.Item2);
        Console.WriteLine("Element 3: " + My_Tuple.Item3);
        Console.WriteLine("Element 4: " + My_Tuple.Item4);
    }
}
```

### 输出

```cs
Element 1: GeeksforGeeks
Element 2: 10
Element 3: G
Element 4: 20.4
```

## 使用 `Create` 方法

您也可以借助 `Create` 方法创建 4 元组。当你使用这个方法时，那么就不需要指定存储在元组中的元素的类型。

### 语法

> `public static Tuple<T1, T2, T3, T4> Create<T1, T2, T3, T4> (T1 item1, T2 item2, T3 item3, T4 item4);`

### 类型参数

*   `T1`：是第一个元组成分的类型。
*   `T2`：是第二元组成分的类型。
*   `T3`：是三元组成分的类型。
*   `T4`：是第四元组成分的类型。

### 参数

*   `item1`：是第一个元组成分的值。
*   `item2`：是第二元组分量的值。
*   `item3`：是第三元组分量的值。
*   `item4`：是第四元组分量的值。

### 返回类型

该方法返回 4 元组，其值为 `item1`、`item2`、`item3`、`item4`。

### 示例

```cs
// C# program to create 4-tuple
// using create method
using System;

public class GFG {

// Main method
    static public void Main()
    {

// Creating tuple with four elements
        // Using Create method
        var My_Tuple = Tuple.Create("Geeks", 20, 'f', 340.6);

        Console.WriteLine("Element 1: " + My_Tuple.Item1);
        Console.WriteLine("Element 2: " + My_Tuple.Item2);
        Console.WriteLine("Element 3: " + My_Tuple.Item3);
        Console.WriteLine("Element 4: " + My_Tuple.Item4);
    }
}
```

### 输出

```cs
Element 1: Geeks
Element 2: 20
Element 3: f
Element 4: 340.6
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.tuple-4.-ctor?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.tuple-4.-ctor?view=netframework-4.8)
*   [https://docs.microsoft.com/en-us/dotnet/api/system.tuple.create?view=netframework-4.8#System_Tuple_Create__4___0___1___2___3_](https://docs.microsoft.com/en-us/dotnet/api/system.tuple.create?view=netframework-4.8#System_Tuple_Create__4___0___1___2___3_)