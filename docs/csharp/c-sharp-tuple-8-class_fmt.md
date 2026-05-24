# C# Tuple<T1, T2, T3, T4, T5, T6, T7, TRest> 类

> 原文: [https://www.geeksforgeeks.org/c-sharp-tuple-8-class/](https://www.geeksforgeeks.org/c-sharp-tuple-8-class/)

`Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 类用于创建 n = 8 或大于 8 的 n 元组。它表示包含八个或八个以上元素的元组。您可以通过调用 [`Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>(T1, T2, T3, T4, T5, T6, T7, TRest)` 构造函数](https://www.geeksforgeeks.org/how-to-create-8-tuple-or-octuple-in-c-sharp/# Using%20Tuple%3CT1,T2,T3,T4,T5,T6,T7,TRest%3E(T1,%20T2,%20T3,%20T4,%20T5,%20T6,%20T7,%20TRest)%20Constructor) 或静态 [`Tuple.Create()` 方法](https://www.geeksforgeeks.org/how-to-create-8-tuple-or-octuple-in-c-sharp/# Using%20the%20Create%20method) 来实例化 `Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 对象。您可以使用只读的 `Item1`、`Item2`、`Item3`、`Item4`、`Item5`、`Item6`、`Item7` 和 `Rest` 实例属性来检索元组元素的值。

## 要点

*   它实现了 `IStructuralComparable`、`IStructuralEquatable` 和 `IComparable` 接口。
*   它是在 `System` 命名空间下定义的。
*   借助嵌套，您可以在一个元组中创建八个以上的元素。您可以在 `Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 中的 `Rest` 参数处创建一个嵌套元组。
*   它将多个数据表示成一个数据集。
*   它允许我们创建、操作和访问数据集。
*   它从一个方法返回多个值，而不使用 `out` 参数。
*   它允许在单个参数的帮助下向一个方法传递多个值。
*   它还可以存储重复的元素。

## 构造器

| 构造器 | 描述 |
| --- | --- |
| [`Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>(T1, T2, T3, T4, T5, T6, T7, TRest)`](https://www.geeksforgeeks.org/how-to-create-8-tuple-or-octuple-in-c-sharp/# Using%20Tuple%3CT1,T2,T3,T4,T5,T6,T7,TRest%3E(T1,%20T2,%20T3,%20T4,%20T5,%20T6,%20T7,%20TRest)%20Constructor) | 初始化 `Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 类的新实例。 |

## 属性

| 属性 | 描述 |
| --- | --- |
| [`Item1`](https://www.geeksforgeeks.org/c-sharp-how-to-get-first-element-of-the-tuple/) | 获取 `Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 对象的第一个元素的值。 |
| [`Item2`](https://www.geeksforgeeks.org/c-sharp-how-to-get-second-element-of-the-tuple/) | 获取当前 `Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 对象的第二个元素的值。 |
| [`Item3`](https://www.geeksforgeeks.org/c-sharp-how-to-get-third-element-of-the-tuple/) | 获取当前 `Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 对象的第三个元素的值。 |
| [`Item4`](https://www.geeksforgeeks.org/c-sharp-how-to-get-fourth-element-of-the-tuple/) | 获取当前 `Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 对象的第四个元素的值。 |
| [`Item5`](https://www.geeksforgeeks.org/c-sharp-sharp-how-to-get-fifth-element-of-the-tuple/) | 获取当前 `Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 对象的第五个元素的值。 |
| [`Item6`](https://www.geeksforgeeks.org/c-sharp-how-to-get-sixth-element-of-the-tuple/) | 获取当前 `Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 对象的第六个元素的值。 |
| [`Item7`](https://www.geeksforgeeks.org/c-sharp-how-to-get-seventh-element-of-the-tuple/) | 获取当前 `Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 对象的第七个元素的值。 |
| [`Rest`](https://www.geeksforgeeks.org/c-sharp-how-to-get-the-remaining-elements-of-the-tuple/) | 获取当前 `Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 对象的剩余元素。 |

## 示例

```cs
// C# program to illustrate the constructor
// and property of Tuple<T1, T2, T3, T4,
// T5, T6, T7, TRest> Class
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // Creating 8-Tuple
        // Using Tuple<T1, T2, T3, T4, T5, T6, T7,
        // TRest>(T1, T2, T3, T4, T5, T6, T7,
        // TRest) constructor
        Tuple<int, int, int, string, int, string, int, Tuple<int, int>> mytuple = new Tuple<int,
                   int, int, string, int, string, int, Tuple<int, int> >(79, 34, 67, "Geeks", 44,
                                           "GeeksforGeeks", 66, new Tuple<int, int>(89, 77));

       // Accessing the values
        Console.WriteLine("Value of the First Component: " + mytuple.Item1);
        Console.WriteLine("Value of the Second Component: " + mytuple.Item2);
        Console.WriteLine("Value of the Third Component: " + mytuple.Item3);
        Console.WriteLine("Value of the Fourth Component: " + mytuple.Item4);
        Console.WriteLine("Value of the Fifth Component: " + mytuple.Item5);
        Console.WriteLine("Value of the Sixth Component: " + mytuple.Item6);
        Console.WriteLine("Value of the Seventh Component: " + mytuple.Item7);
        Console.WriteLine("Value of the Eighth Component: " + mytuple.Rest);

    }
}
```

**Output:**

```cs
Value of the First Component: 79
Value of the Second Component: 34
Value of the Third Component: 67
Value of the Fourth Component: Geeks
Value of the Fifth Component: 44
Value of the Sixth Component: GeeksforGeeks
Value of the Seventh Component: 66
Value of the Eighth Component: (89, 77)
```

## 方法

| 方法 | 描述 |
| --- | --- |
| [`Equals(Object)`](https://www.geeksforgeeks.org/c-sharp-check-if-two-tuple-objects-are-equal/) | 返回一个值，该值指示当前 `Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 对象是否等于指定对象。 |
| [`GetHashCode()`](https://www.geeksforgeeks.org/c-sharp-how-to-get-the-hashcode-of-the-tuple/) | 返回当前 `Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 对象的哈希代码。 |
| [`GetType()`](https://www.geeksforgeeks.org/c-sharp-getting-the-type-of-the-tuples-element/) | 获取当前实例的类型。 |
| `MemberwiseClone()` | 创建当前对象的浅拷贝。 |
| `ToString()` | 返回表示该 `Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 实例的值的字符串。 |

## 示例

```cs
// C# program to check whether the
// given tuples are equal or not
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating 8-Tuple
        // Using Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>(T1,
        // T2, T3, T4, T5, T6, T7, TRest) constructor
        Tuple<int, int, int, int, int, int, int, Tuple<string> > mytuple1 = new Tuple<int,
                                 int, int, int, int, int, int, Tuple<string> >(20, 40, 90,
                                       89, 33, 66, 87, new Tuple<string>("GeeksforGeeks"));

        Tuple<int, int, int, int, int, int, int, Tuple<string> > mytuple2 = new Tuple<int,
                                 int, int, int, int, int, int, Tuple<string> >(20, 40, 90,
                                          89, 33, 66, 87, new Tuple<string>("GeeksforGeeks"));

        // Using Equals method
        if (mytuple1.Equals(mytuple2))
        {
            Console.WriteLine("Tuple Matched.");
        }

        else
        {
            Console.WriteLine("Tuple Not Matched.");
        }
    }
}
```

**Output:**

```cs
Tuple Matched.
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.tuple-8?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.tuple-8?view=netframework-4.8)