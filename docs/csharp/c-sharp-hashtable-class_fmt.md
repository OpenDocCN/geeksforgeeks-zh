# C# 哈希表类

> 原文：[https://www.geeksforgeeks.org/c-sharp-hashtable-class/](https://www.geeksforgeeks.org/c-sharp-hashtable-class/)

`Hashtable` 类表示基于键的哈希代码组织的键/值对的集合。这个类属于 `System.Collections` 命名空间。`Hashtable` 类提供了各种类型的方法，用于对哈希表执行不同类型的操作。在哈希表中，键用于访问集合中的元素。对于非常大的 `Hashtable` 对象，您可以在 64 位系统上将最大容量增加到 20 亿个元素。

## 哈希表类的特征

*   在哈希表中，键不能为空，但值可以为空。
*   在哈希表中，键对象必须是不可变的，只要它们在哈希表中用作键。
*   哈希表的容量是哈希表可以容纳的元素数量。
*   哈希表中的每个键对象都提供了一个哈希函数。

## 构造器

| 构造器 | 描述 |
| --- | --- |
| `Hashtable()` | 使用默认的初始容量、加载因子、哈希代码提供程序和比较器初始化 `Hashtable` 类的新的空实例。 |
| `Hashtable(IDictionary)` | 通过将元素从指定的字典复制到新的 `Hashtable` 对象，初始化 `Hashtable` 类的新实例。新的 `Hashtable` 对象的初始容量等于复制的元素数量，并使用默认的加载因子、哈希代码提供程序和比较器。 |
| `Hashtable(IDictionary, IEqualityComparer)` | 通过将指定字典中的元素复制到新的 `Hashtable` 对象，初始化 `Hashtable` 类的新实例。新的 `Hashtable` 对象的初始容量等于复制的元素数量，并使用默认的加载因子和指定的 `IEqualityComparer` 对象。 |
| `Hashtable(IDictionary, IHashCodeProvider, IComparer)` | 通过将元素从指定的字典复制到新的 `Hashtable` 对象，初始化 `Hashtable` 类的新实例。新的 `Hashtable` 对象的初始容量等于复制的元素数，并使用默认的加载因子以及指定的哈希代码提供程序和比较器。这个 API 已经过时了。有关替代方法，请参见 `Hashtable`。 |
| `Hashtable(IDictionary, Single)` | 通过将元素从指定的字典复制到新的 `Hashtable` 对象，初始化 `Hashtable` 类的新实例。新的 `Hashtable` 对象的初始容量等于复制的元素数，并使用指定的加载因子、默认哈希代码提供程序和比较器。 |
| `Hashtable(IDictionary, Single, IEqualityComparer)` | 通过将元素从指定的字典复制到新的 `Hashtable` 对象，初始化 `Hashtable` 类的新实例。新的 `Hashtable` 对象的初始容量等于复制的元素数量，并使用指定的加载因子和 `IEqualityComparer` 对象。 |
| `Hashtable(IDictionary, Single, IHashCodeProvider, IComparer)` | 通过将元素从指定的字典复制到新的 `Hashtable` 对象，初始化 `Hashtable` 类的新实例。新的 `Hashtable` 对象的初始容量等于复制的元素数，并使用指定的加载因子、哈希代码提供程序和比较器。 |
| `Hashtable(IEqualityComparer)` | 使用默认的初始容量和加载因子以及指定的 `IEqualityComparer` 对象初始化 `Hashtable` 类的新的空实例。 |
| `Hashtable(IHashCodeProvider, IComparer)` | 使用默认的初始容量和加载因子以及指定的哈希代码提供程序和比较器初始化 `Hashtable` 类的新的空实例。 |
| `Hashtable(Int32)` | 使用指定的初始容量、默认加载因子、哈希代码提供程序和比较器初始化 `Hashtable` 类的新的空实例。 |
| `Hashtable(Int32, IEqualityComparer)` | 使用指定的初始容量和 `IEqualityComparer` 以及默认加载因子初始化 `Hashtable` 类的新的空实例。 |
| `Hashtable(Int32, IHashCodeProvider, IComparer)` | 使用指定的初始容量、哈希代码提供程序、比较器和默认加载因子初始化 `Hashtable` 类的新的空实例。 |
| `Hashtable(Int32, Single)` | 使用指定的初始容量和加载因子以及默认哈希代码提供程序和比较器初始化 `Hashtable` 类的新的空实例。 |
| `Hashtable(Int32, Single, IEqualityComparer)` | 使用指定的初始容量、加载因子和 `IEqualityComparer` 对象初始化 `Hashtable` 类的新的空实例。 |
| `Hashtable(Int32, Single, IHashCodeProvider, IComparer)` | 使用指定的初始容量、加载因子、哈希代码提供程序和比较器初始化 `Hashtable` 类的新的空实例。 |
| `Hashtable(SerializationInfo, StreamingContext)` | 使用指定的 `SerializationInfo` 和 `StreamingContext` 对象初始化可序列化的 `Hashtable` 类的新的空实例。 |

**示例：**

```cs
// C# program to create Hashtable
using System;
using System.Collections;

class GFG {

    // Main method
    static void Main(string[] args)
    {

        // create and initialize Hash table
        // using Add() method
        Hashtable g = new Hashtable();
        g.Add(1, "welcome");
        g.Add(2, "to");
        g.Add(3, "tutorials");
        g.Add(4, "of");
        g.Add(5, "C#");

        ICollection key = g.Keys;

        // Print Hash table
        Console.WriteLine("Hashtable:");
        Console.WriteLine();
        foreach(var val in key)
        {
            Console.WriteLine(val + "-" + g[val]);
        }
    }
}
```

**输出：**

```cs
Hashtable:

5-C#
4-of
3-tutorials
2-to
1-welcome
```

## 性能

| 属性 | 描述 |
| --- | --- |
| `Comparer` | 获取或设置用于哈希表的 `IComparer`。 |
| [`Count`](https://www.geeksforgeeks.org/c-count-the-number-of-key-value-pairs-in-the-hashtable/) | 获取哈希表中包含的键/值对的数量。 |
| `EqualityComparer` | 获取用于哈希表的 `IEqualityComparer`。 |
| `Hcp` | 获取或设置可以分配哈希代码的对象。 |
| [`IsFixedSize`](https://www.geeksforgeeks.org/c-check-if-hashtable-has-a-fixed-size/) | 获取一个值，该值指示哈希表是否具有固定大小。 |
| [`IsReadOnly`](https://www.geeksforgeeks.org/c-check-if-hashtable-is-read-only/) | 获取一个值，该值指示哈希表是否为只读。 |
| [`IsSynchronized`](https://www.geeksforgeeks.org/c-check-if-hashtable-is-synchronized-thread-safe/) | 获取一个值，该值指示对哈希表的访问是否同步（线程安全）。 |
| [`Item`](https://www.geeksforgeeks.org/c-get-or-set-the-value-associated-with-specified-key-in-hashtable/) | 获取或设置与指定键关联的值。 |
| [`Keys`](https://www.geeksforgeeks.org/c-gets-an-icollection-containing-the-keys-in-the-hashtable/) | 获取包含哈希表中的键的 `ICollection`。 |
| `SyncRoot` | 获取可用于同步对哈希表的访问的对象。 |
| [`Values`](https://www.geeksforgeeks.org/c-gets-an-icollection-containing-the-values-in-the-hashtable/) | 获取包含哈希表中的值的 `ICollection`。 |

**示例：**

```cs
// C# Program to illustrate the
// Properties of Hashtable
using System;
using System.Collections;

class GFG {

    // Main method
    static void Main(string[] args)
    {

        // create and initialize Hash table
        // using Add() method
        Hashtable has1 = new Hashtable();
        has1.Add("1", "Welcome");
        has1.Add("2", "to");
        has1.Add("3", "geeks");
        has1.Add("4", "for");
        has1.Add("5", "geeks");

        // --------- Using IsSynchronized Property

        // Creating a synchronized packing
        // around the Hashtable
        Hashtable has2 = Hashtable.Synchronized(has1);

        // print the status of both Hashtables
        Console.WriteLine("has1 Hashtable is {0}.",
             has1.IsSynchronized ? "synchronized" :
                               "not synchronized");

        Console.WriteLine("has2 Hashtable is {0}.",
             has2.IsSynchronized ? "synchronized" :
                               "not synchronized");

        // --------- Using Count Property

        Console.WriteLine("Total Number of Elements in has1: "
                                                + has1.Count);
    }
}
```

**输出：**

```cs
has1 Hashtable is not synchronized.
has2 Hashtable is synchronized.
Total Number of Elements in has1: 5
```

## 方法

| 方法 | 描述 |
| --- | --- |
| [`Add(Object, Object)`](https://www.geeksforgeeks.org/c-adding-an-element-into-the-hashtable/) | 将具有指定键和值的元素添加到哈希表中。 |
| [`Clear()`](https://www.geeksforgeeks.org/c-remove-all-elements-from-the-hashtable/) | 从哈希表中移除所有元素。 |
| [`Clone()`](https://www.geeksforgeeks.org/how-to-create-a-shallow-copy-of-hashtable-in-c-sharp/) | 创建哈希表的浅层副本。 |
| [`Contains(Object)`](https://www.geeksforgeeks.org/c-check-whether-a-hashtable-contains-a-specific-key-or-not/) | 确定哈希表是否包含特定的键。 |
| [`ContainsKey(Object)`](https://www.geeksforgeeks.org/c-check-if-the-hashtable-contains-a-specific-key/) | 确定哈希表是否包含特定的键。 |
| [`ContainsValue(Object)`](https://www.geeksforgeeks.org/c-check-if-the-hashtable-contains-a-specific-value/) | 确定哈希表是否包含特定值。 |
| [`CopyTo(Array, Int32)`](https://www.geeksforgeeks.org/c-copying-the-hashtable-elements-to-an-array-instance/) | 将哈希表元素复制到指定索引处的一维数组实例。 |
| [`Equals(Object)`](https://www.geeksforgeeks.org/c-check-if-a-hashtable-is-equal-to-another-hashtable/) | 确定指定的对象是否等于当前对象。 |
| [`GetEnumerator()`](https://www.geeksforgeeks.org/c-get-an-enumerator-that-iterates-through-the-hashtable/) | 返回一个迭代哈希表的 `IDictionaryEnumerator`。 |
| [`GetHash(Object)`](https://www.geeksforgeeks.org/c-sharp-how-to-get-hash-code-for-the-specified-key-of-a-hashtable/) | 返回指定键的哈希代码。 |
| `GetHashCode()` | 用作默认哈希函数。 |
| `GetObjectData(SerializationInfo, StreamingContext)` | 实现 `ISerializable` 接口并返回序列化哈希表所需的数据。 |
| `GetType()` | 获取当前实例的类型。 |
| `KeyEquals(Object, Object)` | 将特定对象与哈希表中的特定键进行比较。 |
| `MemberwiseClone()` | 创建当前对象的浅拷贝。 |
| `OnDeserialization(Object)` | 实现 `ISerializable` 接口，并在反序列化完成时引发反序列化事件。 |
| [`Remove(Object)`](https://www.geeksforgeeks.org/c-remove-the-element-with-the-specified-key-from-the-hashtable/) | 从哈希表中移除具有指定键的元素。 |
| [`Synchronized(Hashtable)`](https://www.geeksforgeeks.org/c-creating-a-synchronized-thread-safe-wrapper-for-the-hashtable/) | 返回哈希表的同步（线程安全）包装。 |
| `ToString()` | 返回表示当前对象的字符串。 |

**示例：**

## C#

### 代码示例

```cs
// C# program to illustrate Add()
// and Remove() Methods
using System;
using System.Collections;

class Program {

    // Main method
    static void Main(string[] args)
    {

        // -------- Add() Method --------

        // create and initialize Hash table
        // using Add() method
        Hashtable g = new Hashtable();
        g.Add("1", "Welcome");
        g.Add("2", "to");
        g.Add("3", "Geeks");
        g.Add("4", "for");
        g.Add("5", "Geeks");

        ICollection key = g.Keys;

        // Print Hash table
        Console.WriteLine("Hashtable Contains:");

        foreach(var val in key)
        {
            Console.WriteLine(val + "-" + g[val]);
        }

        Console.WriteLine();

        // --------- Remove() Method ----------'

        // Remove element 4
        // using Remove() method
        g.Remove("4");

        // printing updated Hash table
        Console.WriteLine("Hashtable after removing element 4:");

        foreach(var val in key)
        {
            Console.WriteLine(val + "-" + g[val]);
        }
    }
}
```

### 输出

```cs
Hashtable Contains:
2-to
3-Geeks
5-Geeks
1-Welcome
4-for

Hashtable after removing element 4:
2-to
3-Geeks
5-Geeks
1-Welcome
```

### 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable?view=netframework-4.7.2#definition](https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable?view=netframework-4.7.2#definition)