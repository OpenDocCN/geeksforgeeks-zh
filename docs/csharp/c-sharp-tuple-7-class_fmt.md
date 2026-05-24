## C# Tuple<T1, T2, T3, T4, T5, T6, T7> 类

> 原文: [https://www.geeksforgeeks.org/c-sharp-tuple-7-class/](https://www.geeksforgeeks.org/c-sharp-tuple-7-class/)

`Tuple<T1, T2, T3, T4, T5, T6, T7>` 类用于创建 7 元组或七元组。它代表一个包含七个元素的元组。您可以通过调用 [`Tuple<T1, T2, T3, T4, T5, T6, T7>(T1, T2, T3, T4, T5, T6, T7)` 构造函数](https://www.geeksforgeeks.org/how-to-create-7-tuple-or-septuple-in-c-sharp/# Using%20Tuple%3CT1,T2,T3,T4,T5,T6,T7%3E(T1,%20T2,%20T3,%20T4,%20T5,%20T6,%20T7)%20Constructor) 或静态的 [`Create` 方法](https://www.geeksforgeeks.org/how-to-create-7-tuple-or-septuple-in-c-sharp/# Using%20the%20Create%20method) 来实例化 `Tuple<T1, T2, T3, T4, T5, T6, T7>` 对象。您可以使用只读的 `Item1`、`Item2`、`Item3`、`Item4`、`Item5`、`Item6` 和 `Item7` 实例属性来检索元组元素的值。

**要点:**

*   它实现了 `IStructuralEquatable`、`IStructuralComparable`、`IComparable` 接口。
*   它是在 `System` 命名空间下定义的。
*   它将多个数据表示成一个数据集。
*   它允许我们创建、操作和访问数据集。
*   它从一个方法返回多个值，而不使用 `out` 参数。
*   它允许在单个参数的帮助下向一个方法传递多个值。
*   它还可以存储重复的元素。

### 构造器

| 构造器 | 描述 |
| :--- | :--- |
| [`Tuple<T1, T2, T3, T4, T5, T6, T7>(T1, T2, T3, T4, T5, T6, T7)`](https://www.geeksforgeeks.org/how-to-create-7-tuple-or-septuple-in-c-sharp/# Using%20Tuple%3CT1,T2,T3,T4,T5,T6,T7%3E(T1,%20T2,%20T3,%20T4,%20T5,%20T6,%20T7)%20Constructor) | 初始化 `Tuple<T1, T2, T3, T4, T5, T6, T7>` 类的新实例。 |

### 属性

| 属性 | 描述 |
| :--- | :--- |
| [`Item1`](https://www.geeksforgeeks.org/c-sharp-how-to-get-first-element-of-the-tuple/) | 获取 `Tuple<T1, T2, T3, T4, T5, T6, T7>` 对象的第一个分量的值。 |
| [`Item2`](https://www.geeksforgeeks.org/c-sharp-how-to-get-second-element-of-the-tuple/) | 获取当前 `Tuple<T1, T2, T3, T4, T5, T6, T7>` 对象的第二个分量的值。 |
| [`Item3`](https://www.geeksforgeeks.org/c-sharp-how-to-get-third-element-of-the-tuple/) | 获取当前 `Tuple<T1, T2, T3, T4, T5, T6, T7>` 对象的第三个分量的值。 |
| [`Item4`](https://www.geeksforgeeks.org/c-sharp-how-to-get-fourth-element-of-the-tuple/) | 获取当前 `Tuple<T1, T2, T3, T4, T5, T6, T7>` 对象的第四个分量的值。 |
| [`Item5`](https://www.geeksforgeeks.org/c-sharp-sharp-how-to-get-fifth-element-of-the-tuple/) | 获取当前 `Tuple<T1, T2, T3, T4, T5, T6, T7>` 对象的第五个分量的值。 |
| [`Item6`](https://www.geeksforgeeks.org/c-sharp-sharp-how-to-get-sixth-element-of-the-tuple/) | 获取当前 `Tuple<T1, T2, T3, T4, T5, T6, T7>` 对象的第六个分量的值。 |
| [`Item7`](https://www.geeksforgeeks.org/c-sharp-how-to-get-seventh-element-of-the-tuple/) | 获取当前 `Tuple<T1, T2, T3, T4, T5, T6, T7>` 对象的第七个分量的值。 |

### 示例

```cs
// C# program to illustrate the constructor
// and property of Tuple<T1, T2, T3, T4,
// T5, T6, T7> Class
using System;

class GFG {

    // Main Method
    static public void Main () {

        // Creating 7-Tuple
        // Using Tuple<T1, T2, T3, T4, T5, T6,
        // T7>(T1, T2, T3, T4, T5, T6, T7) constructor
        Tuple<int, int, int, string, int, string, int> mytuple = new Tuple<int,
                      int, int, string, int, string, int>(79, 34, 67, "Geeks",
                                                         44, "GeeksforGeeks", 66);

        // Accessing the values
        Console.WriteLine("Value of the First Component: " + mytuple.Item1);
        Console.WriteLine("Value of the Second Component: " + mytuple.Item2);
        Console.WriteLine("Value of the Third Component: " + mytuple.Item3);
        Console.WriteLine("Value of the Fourth Component: " + mytuple.Item4);
        Console.WriteLine("Value of the Fifth Component: " + mytuple.Item5);
        Console.WriteLine("Value of the Sixth Component: " + mytuple.Item6);
        Console.WriteLine("Value of the Seventh Component: " + mytuple.Item7);
    }
}
```

**输出:**

```cs
Value of the First Component: 79
Value of the Second Component: 34
Value of the Third Component: 67
Value of the Fourth Component: Geeks
Value of the Fifth Component: 44
Value of the Sixth Component: GeeksforGeeks
Value of the Seventh Component: 66
```