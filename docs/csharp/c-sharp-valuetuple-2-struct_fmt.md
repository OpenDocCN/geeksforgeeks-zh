# C# ValueTuple<T1, T2> 结构

> 原文: [https://www.geeksforgeeks.org/c-sharp-valuetuple-2-struct/](https://www.geeksforgeeks.org/c-sharp-valuetuple-2-struct/)

`ValueTuple<T1, T2>` 结构用于创建一个二元值元组或 2-ValueTuple。它表示存储两个元素的值元组。它提供了[值元组](https://www.geeksforgeeks.org/valuetuple-in-c-sharp/)的运行时实现。您可以使用 `ValueTuple<T1, T2>(T1, T2)` 构造函数或使用 `ValueTuple.Create(T1, T2)` 方法创建 `ValueTuple` 实例，或者简单地使用括号 `()`。您可以通过使用默认属性来检索值元组的未命名元素的值，或者可以借助命名元素的名称来直接访问它们。

**要点:**

*   它实现了 `IComparable`、`IComparable<ValueTuple<T1, T2>>`、`IEquatable<ValueTuple<T1, T2>>`、`IStructuralComparable`、`IStructuralEquatable` 和 `ITuple` 接口。
*   它是在 `System` 命名空间下定义的。
*   它还可以存储重复的元素。
*   字段是可变的。因此，您可以更改 `ValueTuple<T1, T2>` 的值。
*   在这里，像 `Item1` 和 `Item2` 这样的成员是字段而不是属性。
*   它的值类型不是引用类型。
*   它将多个数据表示成一个数据集。
*   它允许在单个参数的帮助下向一个方法传递多个值。

#### 构造器

| 构造器 | 描述 |
| :--- | :--- |
| `ValueTuple<T1, T2>(T1, T2)` | 初始化一个新的 `ValueTuple<T1, T2>` 实例。 |

#### 字段

| 字段 | 描述 |
| :--- | :--- |
| `Item1` | 获取当前 `ValueTuple<T1, T2>` 实例的第一个元素的值。 |
| `Item2` | 获取当前 `ValueTuple<T1, T2>` 实例的第二个元素的值。 |

**示例:**

```csharp
// C# program to illustrate how to
// access the element of ValueTuple<T1,T2>
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // Creating a value tuple
        // Using Create method
        var Mylibrary = ValueTuple.Create(3456, "The Guide");

        // Display the element of the given value tuple
        Console.WriteLine("Book Details: ");
        Console.WriteLine("Book Id: {0}", Mylibrary.Item1);
        Console.WriteLine("Book Name: {0}", Mylibrary.Item2);
    }
}
```

**输出:**

```csharp
Book Details: 
Book Id: 3456
Book Name: The Guide
```

#### 方法

| 方法 | 描述 |
| :--- | :--- |
| `CompareTo(ValueTuple<T1, T2>)` | 将当前 `ValueTuple<T1, T2>` 实例与指定的 `ValueTuple<T1, T2>` 实例进行比较。 |
| `Equals(Object)` | 返回一个值，该值指示当前 `ValueTuple<T1, T2>` 实例是否等于指定的对象。 |
| `Equals(ValueTuple<T1, T2>)` | 返回一个值，该值指示当前 `ValueTuple<T1, T2>` 实例是否等于指定的 `ValueTuple<T1, T2>` 实例。 |
| `GetHashCode()` | 计算当前 `ValueTuple<T1, T2>` 实例的哈希代码。 |
| `ToString()` | 返回一个字符串，该字符串表示该 `ValueTuple<T1, T2>` 实例的值。 |

**示例:**

```csharp
// C# program to Check the given 
// value tuples are equal or not
using System;

class GFG {

    // Main method
    static public void Main()
    {
        // Creating 2-ValueTuple
        // Using Create method
        var T1 = ValueTuple.Create(346, 784);
        var T2 = ValueTuple.Create(346, 7743);

        // Check if both the value tuples
        // are equal or not
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

**输出:**

```csharp
Incorrect Code...!!
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple-2?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple-2?view=netframework-4.8)