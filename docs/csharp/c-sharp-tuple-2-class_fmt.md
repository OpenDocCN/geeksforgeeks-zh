# C# Tuple<T1,T2> 类

> 原文: [https://www.geeksforgeeks.org/c-sharp-tuple-2-class/](https://www.geeksforgeeks.org/c-sharp-tuple-2-class/)

`Tuple<T1,T2>` 类用于创建二元组或二元对。它表示一个包含两个元素的元组。您可以通过调用 [`Tuple<T1,T2>(T1, T2)` 构造函数](https://www.geeksforgeeks.org/how-to-create-2-tuple-or-pair-tuple-in-c-sharp/# Using%20Tuple%3CT1,T2%3E(T1,%20T2)%20Constructor) 或静态 [`Tuple.Create` 方法](https://www.geeksforgeeks.org/how-to-create-2-tuple-or-pair-tuple-in-c-sharp/# Using%20the%20Create%20method) 来实例化 `Tuple<T1,T2>` 对象。您可以使用只读的 `Item1` 和 `Item2` 实例属性来检索元组元素的值。

**要点:**

*   它实现了 `IStructuralComparable`、`IStructuralEquatable`、`IComparable` 接口。
*   它是在 `System` 命名空间下定义的。
*   它将多个数据表示成一个数据集。
*   它允许我们创建、操作和访问数据集。
*   它从一个方法返回多个值，而不使用 `out` 参数。
*   它允许在单个参数的帮助下向一个方法传递多个值。
*   它还可以存储重复的元素。

## 构造器

| 构造器 | 描述 |
| :--- | :--- |
| [`Tuple<T1, T2>(T1, T2)`](https://www.geeksforgeeks.org/how-to-create-2-tuple-or-pair-tuple-in-c-sharp/# Using%20Tuple%3CT1,T2%3E(T1,%20T2)%20Constructor) | 初始化 `Tuple<T1,T2>` 类的新实例。 |

## 属性

| 属性 | 描述 |
| :--- | :--- |
| [`Item1`](https://www.geeksforgeeks.org/c-sharp-how-to-get-first-element-of-the-tuple/) | 获取 `Tuple<T1,T2>` 对象的第一个分量的值。 |
| [`Item2`](https://www.geeksforgeeks.org/c-sharp-how-to-get-second-element-of-the-tuple/) | 获取当前 `Tuple<T1,T2>` 对象的第二个分量的值。 |

**示例:**

```cs
// C# program to illustrate the constructor
// and property of Tuple<T1,T2> Class
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // Creating 2-Tuple
        // Using Tuple<T1, T2>(T1, T2) constructor
        Tuple<int, int> mytuple = new Tuple<int, int>(79, 80);

        // Accessing the values
        Console.WriteLine("Value of the First Component: " + mytuple.Item1);
        Console.WriteLine("Value of the Second Component: " + mytuple.Item2);
    }
}
```

**Output:**

```cs
Value of the First Component: 79
Value of the Second Component: 80
```

## 方法

| 方法 | 描述 |
| :--- | :--- |
| [`Equals(Object)`](https://www.geeksforgeeks.org/c-sharp-check-if-two-tuple-objects-are-equal/) | 返回一个值，该值指示当前 `Tuple<T1,T2>` 对象是否等于指定对象。 |
| [`GetHashCode()`](https://www.geeksforgeeks.org/c-sharp-how-to-get-the-hashcode-of-the-tuple/) | 返回当前 `Tuple<T1,T2>` 对象的哈希代码。 |
| [`GetType()`](https://www.geeksforgeeks.org/c-sharp-getting-the-type-of-the-tuples-element/) | 获取当前实例的类型。 |
| `MemberwiseClone()` | 创建当前对象的浅拷贝。 |
| `ToString()` | 返回表示该 `Tuple<T1,T2>` 实例的值的字符串。 |

**示例:**

```cs
// C# program to determine whether
// the given tuples are equal or not
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Creating 2-Tuple
        // Using Tuple<T1, T2>(T1, T2) constructor
        Tuple<int, int> mytuple1 = new Tuple<int, int>(20, 40);
        Tuple<int, int> mytuple2 = new Tuple<int, int>(20, 49);

        // Using Equals method
        if (mytuple1.Equals(mytuple2))
        {
            Console.WriteLine("Tuple Matched..");
        }

        else
        {
            Console.WriteLine("Tuple not matched..");
        }
    }
}
```

**Output:**

```cs
Tuple not matched..
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.tuple-2.item1?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.tuple-2.item1?view=netframework-4.8)