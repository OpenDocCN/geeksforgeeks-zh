# C# Tuple<T1, T2, T3>类

> 原文: [https://www.geeksforgeeks.org/c-sharp-tuple-3-class/](https://www.geeksforgeeks.org/c-sharp-tuple-3-class/)

`Tuple<T1, T2, T3>`类用于创建三元组或三元组。它表示一个包含三个元素的元组。您可以通过调用 [`Tuple<T1, T2, T3>(T1, T2, T3)` 构造函数](https://www.geeksforgeeks.org/how-to-create-3-tuple-or-triple-tuple-in-c-sharp/# Using%20Tuple%3CT1,T2,T3%3E(T1,%20T2,%20T3)%20Constructor) 或静态的 [`Create` 方法](https://www.geeksforgeeks.org/how-to-create-3-tuple-or-triple-tuple-in-c-sharp/# Using%20the%20Create%20method) 来实例化 `Tuple<T1, T2, T3>` 对象。您可以使用只读的 `Item1`、`Item2` 和 `Item3` 实例属性来检索元组元素的值。

**要点:**

*   它实现了 `IStructuralEquatable`、`IStructuralComparable`、`IComparable` 接口。
*   它是在 `System` 命名空间下定义的。
*   它将多个数据表示成一个数据集。
*   它允许我们创建、操作和访问数据集。
*   它从一个方法返回多个值，而不使用 `out` 参数。
*   它允许在单个参数的帮助下向一个方法传递多个值。
*   它还可以存储重复的元素。

#### 构造函数

| 构造函数 | 描述 |
| :--- | :--- |
| [`Tuple<T1, T2, T3>(T1, T2, T3)`](https://www.geeksforgeeks.org/how-to-create-3-tuple-or-triple-tuple-in-c-sharp/# Using%20Tuple%3CT1,T2,T3%3E(T1,%20T2,%20T3)%20Constructor) | 初始化 `Tuple<T1, T2, T3>` 类的新实例。 |

#### 属性

| 属性 | 描述 |
| :--- | :--- |
| [`Item1`](https://www.geeksforgeeks.org/c-sharp-how-to-get-first-element-of-the-tuple/) | 获取 `Tuple<T1, T2, T3>` 对象的第一个分量的值。 |
| [`Item2`](https://www.geeksforgeeks.org/c-sharp-how-to-get-second-element-of-the-tuple/) | 获取当前 `Tuple<T1, T2, T3>` 对象的第二个分量的值。 |
| [`Item3`](https://www.geeksforgeeks.org/c-sharp-how-to-get-third-element-of-the-tuple/) | 获取当前 `Tuple<T1, T2, T3>` 对象的第三个分量的值。 |

**示例:**

```cs
// C# program to illustrate the constructor
// and property of Tuple<T1, T2, T3> Class
using System;

class GFG {

    static public void Main()
    {
        // Creating 3-Tuple
        // Using Tuple<T1, T2, T3>(T1,
        // T2, T3) constructor
        Tuple<int, int, int> mytuple = new Tuple<int, int, int>(79, 34, 67);

        // Accessing the values
        Console.WriteLine("Value of the First Component: " + mytuple.Item1);
        Console.WriteLine("Value of the Second Component: " + mytuple.Item2);
        Console.WriteLine("Value of the Third Component: " + mytuple.Item3);

    }
}
```

**Output:**

```cs
Value of the First Component: 79
Value of the Second Component: 34
Value of the Third Component: 67
```

#### 方法

| 方法 | 描述 |
| :--- | :--- |
| [`Equals(Object)`](https://www.geeksforgeeks.org/c-sharp-check-if-two-tuple-objects-are-equal/) | 返回一个值，该值指示当前 `Tuple<T1, T2, T3>` 对象是否等于指定对象。 |
| [`GetHashCode()`](https://www.geeksforgeeks.org/c-sharp-how-to-get-the-hashcode-of-the-tuple/) | 返回当前 `Tuple<T1, T2, T3>` 对象的哈希代码。 |
| [`GetType()`](https://www.geeksforgeeks.org/c-sharp-getting-the-type-of-the-tuples-element/) | 获取当前实例的类型。 |
| `MemberwiseClone()` | 创建当前对象的浅拷贝。 |
| `ToString()` | 返回表示该 `Tuple<T1, T2, T3>` 实例的值的字符串。 |

**示例:**

```cs
// C# program to check whether the
// given tuples are equal or not
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating 3-Tuple
        // Using Tuple<T1, T2, T3>(T1, T2, T3) constructor
        Tuple<int, int, int> mytuple1 = new Tuple<int, int, int>(20, 40, 90);
        Tuple<int, int, int> mytuple2 = new Tuple<int, int, int>(20, 49, 87);

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

*   [https://docs.microsoft.com/en-us/dotnet/api/system.tuple-3?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.tuple-3?view=netframework-4.8)