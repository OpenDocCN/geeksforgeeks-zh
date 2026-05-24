# C# ValueTuple<T1, T2, T3> 结构

> 原文: [https://www.geeksforgeeks.org/c-sharp-valuetuple-3-struct/](https://www.geeksforgeeks.org/c-sharp-valuetuple-3-struct/)

`ValueTuple<T1, T2, T3>` 结构用于创建三值元组或 3 值元组。它表示存储三个元素的值元组。它提供了[值元组](https://www.geeksforgeeks.org/valuetuple-in-c-sharp/)的运行时实现。您可以使用 `ValueTuple<T1, T2, T3>(T1, T2, T3)` 构造函数或使用 `ValueTuple.Create` 方法创建 `ValueTuple<T1, T2, T3>` 结构的实例，或者简单地使用括号 `()`。您可以通过使用默认属性来检索值元组的未命名元素的值，或者可以借助命名元素的名称来直接访问它们。

**要点:**

*   它实现了 `IComparable`、`IComparable<ValueTuple<T1, T2, T3>>`、`IStructuralComparable`、`IStructuralEquatable`、`ITuple` 接口。
*   它是在 `System` 命名空间下定义的。
*   它还可以存储重复的元素。
*   字段是可变的。因此，您可以更改 `ValueTuple<T1, T2, T3>` 的值。
*   在这里，像 `Item1`、`Item2`、`Item3` 这样的成员是字段而不是属性。
*   它的值类型不是引用类型。
*   它将多个数据表示成一个数据集。
*   它允许在单个参数的帮助下向一个方法传递多个值。

## 构造器

| 构造器 | 描述 |
| :--- | :--- |
| `ValueTuple<T1, T2, T3>(T1, T2, T3)` | 初始化一个新的 `ValueTuple<T1, T2, T3>` 实例。 |

## 字段

| 字段 | 描述 |
| :--- | :--- |
| `Item1` | 获取当前 `ValueTuple<T1, T2, T3>` 实例的第一个元素的值。 |
| `Item2` | 获取当前 `ValueTuple<T1, T2, T3>` 实例的第二个元素的值。 |
| `Item3` | 获取当前 `ValueTuple<T1, T2, T3>` 实例的第三个元素的值。 |

**示例:**

```cs
// C# program to illustrate how to
// access the element of ValueTuple<T1, T2, T3>
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // Creating a value tuple
        // Using Create method
        var Mylibrary = ValueTuple.Create(3456,
                "The Guide", "R. K. Narayan");

        // Display the element of the given value tuple
        Console.WriteLine("Book Details: ");
        Console.WriteLine("Book Id: {0}", Mylibrary.Item1);
        Console.WriteLine("Book Name: {0}", Mylibrary.Item2);
        Console.WriteLine("Author Name: {0}", Mylibrary.Item3);
    }
}
```

**Output:**

```cs
Book Details: 
Book Id: 3456
Book Name: The Guide
Author Name: R. K. Narayan
```

## 方法

| 方法 | 描述 |
| :--- | :--- |
| `CompareTo(ValueTuple<T1, T2, T3>)` | 将当前 `ValueTuple<T1, T2, T3>` 实例与指定的 `ValueTuple<T1, T2, T3>` 实例进行比较。 |
| `Equals(Object)` | 返回一个值，该值指示当前 `ValueTuple<T1, T2, T3>` 实例是否等于指定的对象。 |
| `Equals(ValueTuple<T1, T2, T3>)` | 返回一个值，该值指示当前 `ValueTuple<T1, T2, T3>` 实例是否等于指定的 `ValueTuple<T1, T2, T3>` 实例。 |
| `GetHashCode()` | 计算当前 `ValueTuple<T1, T2, T3>` 实例的哈希代码。 |
| `ToString()` | 返回一个字符串，该字符串表示该 `ValueTuple<T1, T2, T3>` 实例的值。 |

**示例:**

```cs
// C# program to check the given 
// value tuples are equal or not
using System;

class GFG {

    // Main method
    static public void Main()
    {
        // Creating 3-ValueTuple
        // Using Create method
        var T1 = ValueTuple.Create(346, 784, 45);
        var T2 = ValueTuple.Create(346, 7743, 56);

        // Check if both the value tuples are equal or not
        if (T1.Equals(T2)) 
        {
            Console.WriteLine("Code is correct...!!");
        }
        else 
        {
            Console.WriteLine("Incorrect Code...!!");
        }
    }
}
```

**Output:**

```cs
Incorrect Code...!!
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple-3?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple-3?view=netframework-4.8)