# C# | Collection类

> 原文: [https://www.geeksforgeeks.org/c-sharp-collection-class/](https://www.geeksforgeeks.org/c-sharp-collection-class/)

`Collection<T>`类为泛型集合提供基类。这里 `T` 是集合中元素的类型。这个类隶属于 `System.Collections.ObjectModel` 命名空间。

## 特征

*   `Collection<T>`类可以通过创建其构造类型之一的实例来立即使用。
*   `Collection<T>`类提供了受保护的方法，可用于在添加和移除项目、清除集合或设置现有项目的值时自定义其行为。
*   大多数 `Collection<T>` 对象都可以修改。但是，用只读 [`IList<T>`](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.ilist-1?view=netframework-4.7.2) 对象初始化的 `Collection` 对象不能修改。
*   可以使用整数索引访问此集合中的元素。该集合中的索引是**从零开始的**。
*   `Collection<T>` 接受 `null` 作为引用类型的有效值，并允许重复元素。

## 构造器

| 构造器 | 描述 |
| :--- | :--- |
| `Collection<T>()` | 初始化 `Collection<T>` 类的新实例，该实例为空。 |
| `Collection<T>(IList<T>)` | 初始化 `Collection<T>` 类的新实例，作为指定列表的包装。 |

**示例:**

```cs
// C# code to create a Collection
using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;

class GFG {

// Driver code
    public static void Main()
    {
        // Creating a collection of ints
        Collection<int> myColl = new Collection<int>();

        // Adding elements in Collection myColl
        myColl.Add(2);
        myColl.Add(3);
        myColl.Add(4);
        myColl.Add(5);

        // Displaying the elements in myColl
        foreach(int i in myColl)
        {
            Console.WriteLine(i);
        }
    }
}
```

**输出:**

```cs

```

## 属性

| 属性 | 描述 |
| :--- | :--- |
| [`Count`](https://www.geeksforgeeks.org/c-get-the-number-of-elements-contained-in-collectiont/) | 获取 `Collection<T>` 中实际包含的元素数量。 |
| `Items` | 获取集合周围的 `IList<T>` 包装器。 |
| [`Item[Int32]`](https://www.geeksforgeeks.org/c-get-or-set-the-element-at-specified-index-in-collectiont/) | 获取或设置指定索引处的元素。 |

**示例:**

```cs
// C# Code to illustrate the 
// Properties of Collection class
using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;

class GFG {

// Driver code
    public static void Main()
    {

        // Creating a collection of strings
        Collection<string> myColl = new Collection<string>();

        // Adding elements in Collection myColl
        myColl.Add("A");
        myColl.Add("B");
        myColl.Add("C");
        myColl.Add("D");
        myColl.Add("E");

        // ------- Count Property ----------

        // To print the count of
        // elements in Collection
        Console.WriteLine("Count : " + myColl.Count);

        // -------- Item[Int32] Property --------

        // Get the element at index 2
        Console.WriteLine("Element at index 2 is : " + myColl[2]);

        // Get the element at index 3
        Console.WriteLine("Element at index 3 is : " + myColl[3]);
    }
}
```

**输出:**

```cs
Count : 5
Element at index 2 is : C
Element at index 3 is : D
```

## 方法

| 方法 | 描述 |
| :--- | :--- |
| [`Add(T)`](https://www.geeksforgeeks.org/c-add-an-object-to-the-end-of-collectiont/) | 将对象添加到 `Collection<T>` 的末尾。 |
| [`Clear()`](https://www.geeksforgeeks.org/c-remove-all-elements-from-the-collectiont/) | 从 `Collection<T>` 中移除所有元素。 |
| `ClearItems()` | 从 `Collection<T>` 中移除所有元素。 |
| [`Contains(T)`](https://www.geeksforgeeks.org/c-check-if-an-element-is-in-the-collectiont/) | 确定一个元素是否在 `Collection<T>` 中。 |
| [`CopyTo(T[], Int32)`](https://www.geeksforgeeks.org/c-copying-the-collectiont-elements-to-an-array/) | 从目标数组的指定索引开始，将整个 `Collection<T>` 复制到兼容的一维数组。 |
| `Equals(Object)` | 确定指定的对象是否等于当前对象。 |
| `GetEnumerator()` | 返回遍历 `Collection<T>` 的枚举数。 |
| `GetHashCode()` | 用作默认哈希函数。 |
| `GetType()` | 获取当前实例的类型。 |
| `IndexOf(T)` | 搜索指定的对象，并返回整个集合中第一个匹配项的从零开始的索引。 |
| [`Insert(Int32, T)`](https://www.geeksforgeeks.org/c-insert-an-element-into-collectiont-at-specified-index/) | 在集合中的指定索引处插入一个元素。 |
| `InsertItem(Int32, T)` | 将元素插入集合中的指定索引处。 |
| `MemberwiseClone()` | 创建当前对象的浅拷贝。 |
| [`Remove(T)`](https://www.geeksforgeeks.org/c-removing-first-occurrence-of-object-from-collectiont/) | 从 `Collection<T>` 中移除特定对象的第一次出现。 |
| [`RemoveAt(Int32)`](https://www.geeksforgeeks.org/c-remove-element-at-specified-index-of-collectiont/) | 移除集合指定索引处的元素。 |
| `RemoveItem(Int32)` | 移除集合指定索引处的元素。 |
| `SetItem(Int32, T)` | 替换指定索引处的元素。 |
| `ToString()` | 返回表示当前对象的字符串。 |

**示例:**

```cs
// C# code to check if an
// element is in the Collection
using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;

class GFG {

// Driver code
    public static void Main()
    {
        // Creating a collection of strings
        Collection<string> myColl = new Collection<string>();

        myColl.Add("A");
        myColl.Add("B");
        myColl.Add("C");
        myColl.Add("D");
        myColl.Add("E");

        // Checking if an element is in the Collection
        // The function returns "True" if the
        // item is present in Collection
        // else returns "False"
        Console.WriteLine(myColl.Contains("A"));
    }
}
```

**输出:**

```cs
True
```

**例 2:**

```cs
// C# code to copy the entire Collection
// to a compatible one-dimensional Array,
// starting at the specified index of
// the target array
using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;

class GFG {

// Driver code
    public static void Main()
    {
        // Creating a collection of strings
        Collection<string> myColl = new Collection<string>();

        myColl.Add("A");
        myColl.Add("B");
        myColl.Add("C");
        myColl.Add("D");
        myColl.Add("E");

        // Creating a string array
        string[] myArr = new string[myColl.Count];

        // Copying the entire Collection to a
        // compatible one-dimensional Array,
        // starting at the specified index
        // of the target array
        myColl.CopyTo(myArr, 0);

        // Displaying the elements in myArr
        foreach(string str in myArr)
        {
            Console.WriteLine(str);
        }
    }
}
```

**输出:**

```cs
A
B
C
D
E
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.collection-1?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.collection-1?view=netframework-4.7.2)