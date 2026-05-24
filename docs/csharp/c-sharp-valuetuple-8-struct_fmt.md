# C# | ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest> 结构

> 原文: [https://www.geeksforgeeks.org/c-sharp-valuetuple-8-struct/](https://www.geeksforgeeks.org/c-sharp-valuetuple-8-struct/)

`ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 结构用于创建 n 值元组，其中 n = 8 或大于 8。它表示包含八个或八个以上元素的值元组。它提供了[值元组](https://www.geeksforgeeks.org/valuetuple-in-c-sharp/)的运行时实现。您可以使用 `ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>(T1, T2, T3, T4, T5, T6, T7, TRest)` 构造器，或使用 `ValueTuple.Create` 方法，或简单地使用括号 `()` 来创建 `ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 的实例。您可以通过使用默认属性来检索值元组的未命名元素的值，或者可以借助命名元素的名称来直接访问它们。

## 要点

*   它实现了 `IStructuralEquatable`、`IStructuralComparable`、`IComparable`、`IComparable<ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>>` 和 `ITuple` 接口。
*   它是在 `System` 命名空间下定义的。
*   它还可以存储重复的元素。
*   字段是可变的。因此，您可以更改 `ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 的值。
*   这里的成员有 `Item1`、`Item2`、`Item3`、`Item4`、`Item5`、`Item6`、`Item7` 等，是字段而不是属性。
*   它是值类型，不是引用类型。
*   它将多个数据表示成一个数据集。
*   它允许在单个参数的帮助下向一个方法传递多个值。

### 构造器

| 构造器 | 描述 |
| --- | --- |
| `ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>(T1, T2, T3, T4, T5, T6, T7, TRest)` | 初始化一个新的 `ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 实例。 |

### 字段

| 字段 | 描述 |
| --- | --- |
| `Item1` | 获取当前 `ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 实例的第一个元素的值。 |
| `Item2` | 获取当前 `ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 实例的第二个元素的值。 |
| `Item3` | 获取当前 `ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 实例的第三个元素的值。 |
| `Item4` | 获取当前 `ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 实例的第四个元素的值。 |
| `Item5` | 获取当前 `ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 实例的第五个元素的值。 |
| `Item6` | 获取当前 `ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 实例的第六个元素的值。 |
| `Item7` | 获取当前 `ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 实例的第七个元素的值。 |
| `Rest` | 定义元组剩余元素类型的任何泛型值元组实例。 |

**示例:**

```cs
// C# program to illustrate how to
// access the element of ValueTuple<T1,
// T2, T3, T4, T5, T6, T7, TRest>
using System;

class GFG {

// Main Method
    static public void Main()
    {

// Creating a value tuple
        // Using Create method
        var Mylibrary = ValueTuple.Create(3456, "The Guide", "R. K. Narayan",
                             1958, "Philosophical novel", "English", "India",
                  ValueTuple.Create("Swami and Friends", "The Dark Room",
                                   "Mr. Sampath", "Grandmother's Tale"));

// Display the element of the given value tuple
        Console.WriteLine("Book Details: ");
        Console.WriteLine("Book Id: {0}", Mylibrary.Item1);
        Console.WriteLine("Book Name: {0}", Mylibrary.Item2);
        Console.WriteLine("Author Name: {0}", Mylibrary.Item3);
        Console.WriteLine("Publication date: {0}", Mylibrary.Item4);
        Console.WriteLine("Gener: {0}", Mylibrary.Item5);
        Console.WriteLine("Language: {0}", Mylibrary.Item6);
        Console.WriteLine("Country: {0}", Mylibrary.Item7);
        Console.WriteLine("Other Novels: {0}", Mylibrary.Rest);
    }
}
```

**输出:**

```cs
Book Details:
Book Id: 3456
Book Name: The Guide
Author Name: R. K. Narayan
Publication date: 1958
Gener: Philosophical novel
Language: English
Country: India
Other Novels: ((Swami and Friends, The Dark Room, Mr. Sampath, Grandmother's Tale))
```

### 方法

| 方法 | 描述 |
| --- | --- |
| `CompareTo(ValueTuple)` | 将当前 `ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 实例与指定的 `ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 实例进行比较。 |
| `Equals(Object)` | 返回一个值，该值指示当前 `ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 实例是否等于指定的对象。 |
| `Equals(ValueTuple)` | 返回一个值，该值指示当前 `ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 实例是否等于指定的 `ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 实例。 |
| `GetHashCode()` | 计算当前 `ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 实例的哈希代码。 |
| `ToString()` | 返回一个字符串，该字符串表示该 `ValueTuple<T1, T2, T3, T4, T5, T6, T7, TRest>` 实例的值。 |

**示例:**

```cs
// C# program to check the given
// value tuples are equal or not
using System;

class GFG {

// Main method
    static public void Main()
    {

// Creating 8-ValueTuple
        // Using Create method
        var T1 = ValueTuple.Create(3, 2, 4, 5, 6, 7, 6, 10);
        var T2 = ValueTuple.Create(3, 2, 4, 5, 6, 7, 6, 1);

// Check if both the value
        // tuples are equal or not
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

```cs
Incorrect Code...!!
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple-8?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple-8?view=netframework-4.8)