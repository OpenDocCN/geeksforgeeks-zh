# 如何在 C# 中创建 8 元组或八元组？

> 原文：[https://www.geeksforgeeks.org/how-to-create-8-tuple-or-octuple-in-c-sharp/](https://www.geeksforgeeks.org/how-to-create-8-tuple-or-octuple-in-c-sharp/)

在 C# 中，8 元组是包含 8 个元素的[元组](https://www.geeksforgeeks.org/c-sharp-tuple/)，也称为**八元组**。您可以使用两种不同的方法创建 8 元组：

*   [使用 `Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>(T1, T2, T3, T4, T5, T6, T7, TRest)` 构造器](#使用-tuplet1-t2-t3-t4-t5-t6-t7-trestt1-t2-t3-t4-t5-t6-t7-trest-构造器)
*   [使用 `Create` 方法](#使用-create-方法)

## 使用 `Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>(T1, T2, T3, T4, T5, T6, T7, TRest)` 构造器

可以使用 `Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>(T1, T2, T3, T4, T5, T6, T7, TRest)` 构造器创建 8 元组。它初始化 `Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 类的一个新实例。但是当你使用这个构造函数创建一个元组时，那么*你必须指定存储在元组中的元素*的类型。

**注意：** 如果你会这个构造函数，那么你也可以使用 `rest` 参数创建一个包含八个或八个以上元素的元组，创建 n 个嵌套的元组，每个元组包含一到七个组件。

### 语法

> `public Tuple(T1 item1, T2 item2, T3 item3, T4 item4, T5 item5, T6 item6, T7 item7, TRest rest);`

### 参数

*   `item1`：是第一个元组成分的值。
*   `item2`：是第二元组分量的值。
*   `item3`：是第三元组分量的值。
*   `item4`：是第四元组分量的值。
*   `item5`：是第五元组分量的值。
*   `item6`：是第六元组分量的值。
*   `item7`：是第七元组分量的值。
*   `rest`：它是任何包含元组剩余组件值的通用元组对象。

**异常：** 如果 `rest` 不是通用元组对象，这将给出 `ArgumentException`。

### 示例

```cs
// C# program to create 8-tuple
// using the tuple constructor
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Creating tuple with eight elements
        // Using Tuple<T1, T2, T3, T4, T5, T6,
        // T7, TRest>(T1, T2, T3, T4, T5, T6,
        // T7, TRest) constructor
        Tuple<int, int, int, int, int, int, int, Tuple<int>> My_Tuple = new Tuple<int,
                       int, int, int, int, int, int, Tuple<int> >(22, 33, 44, 545, 55,
                                                 88, 66, new Tuple<int>(77));

        Console.WriteLine("Element 1: " + My_Tuple.Item1);
        Console.WriteLine("Element 2: " + My_Tuple.Item2);
        Console.WriteLine("Element 3: " + My_Tuple.Item3);
        Console.WriteLine("Element 4: " + My_Tuple.Item4);
        Console.WriteLine("Element 5: " + My_Tuple.Item5);
        Console.WriteLine("Element 6: " + My_Tuple.Item6);
        Console.WriteLine("Element 7: " + My_Tuple.Item7);
        Console.WriteLine("Element 8: " + My_Tuple.Rest.Item1);
    }
}
```

### Output

```cs
Element 1: 22
Element 2: 33
Element 3: 44
Element 4: 545
Element 5: 55
Element 6: 88
Element 7: 66
Element 8: 77
```

## 使用 `Create` 方法

您也可以借助 `Create` 方法创建 8 元组。当你使用这个方法时，那么*就不需要指定存储在元组中的元素的类型*。

### 语法

> `public static Tuple<T1, T2, T3, T4, T5, T6, T7, Tuple<T8>> Create<T1, T2, T3, T4, T5, T6, T7, T8>(T1 item1, T2 item2, T3 item3, T4 item4, T5 item5, T6 item6, T7 item7, T8 item8);`

### 类型参数

*   `T1`：是第一个元组成分的类型。
*   `T2`：是第二元组成分的类型。
*   `T3`：是三元组成分的类型。
*   `T4`：是第四元组成分的类型。
*   `T5`：是第五元组成分的类型。
*   `T6`：是第六元组成分的类型。
*   `T7`：是第七元组成分的类型。
*   `T8`：是第八元组成分的类型。

### 参数

*   `item1`：是第一个元组成分的值。
*   `item2`：是第二元组分量的值。
*   `item3`：是第三元组分量的值。
*   `item4`：是第四元组分量的值。
*   `item5`：是第五元组分量的值。
*   `item6`：是第六元组分量的值。
*   `item7`：是第七元组分量的值。
*   `item8`：是第八元组分量的值。

**返回类型：** 该方法返回 8 元组，其值为 `item1`、`item2`、`item3`、`item4`、`item5`、`item6`、`item7` 和 `item8`。

### 示例

```cs
// C# program to create 8-tuple
// using create method
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Creating tuple with eight
        // elements Using Create method
        var My_Tuple = Tuple.Create("C", "C++", "Ruby",
             "Java", "Perl", "PHP", "Python", "Scala");

        Console.WriteLine("Element 1: " + My_Tuple.Item1);
        Console.WriteLine("Element 2: " + My_Tuple.Item2);
        Console.WriteLine("Element 3: " + My_Tuple.Item3);
        Console.WriteLine("Element 4: " + My_Tuple.Item4);
        Console.WriteLine("Element 5: " + My_Tuple.Item5);
        Console.WriteLine("Element 6: " + My_Tuple.Item6);
        Console.WriteLine("Element 7: " + My_Tuple.Item7);
        Console.WriteLine("Element 8: " + My_Tuple.Rest);
    }
}
```

### Output

```cs
Element 1: C
Element 2: C++
Element 3: Ruby
Element 4: Java
Element 5: Perl
Element 6: PHP
Element 7: Python
Element 8: (Scala)
```

### 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.tuple-8.-ctor?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.tuple-8.-ctor?view=netframework-4.8)
*   [https://docs.microsoft.com/en-us/dotnet/api/system.tuple.create?view=netframework-4.8#System_Tuple_Create__8___0___1___2___3___4___5___6___7_](https://docs.microsoft.com/en-us/dotnet/api/system.tuple.create?view=netframework-4.8#System_Tuple_Create__8___0___1___2___3___4___5___6___7_)