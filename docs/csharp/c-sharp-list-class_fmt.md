# C# |列表类

> 原文:[https://www.geeksforgeeks.org/c-sharp-list-class/](https://www.geeksforgeeks.org/c-sharp-list-class/)

`List<T>`类代表可以通过索引访问的对象列表。它属于`System.Collections.Generic`命名空间。`List`类可以用来创建不同类型的集合，如整数、字符串等。`List<T>`类还提供了搜索、排序和操作列表的方法。

**特征:**

*   它不同于数组。`List<T>`可以动态调整大小，但是数组不能。
*   `List<T>`类可以接受`null`作为引用类型的有效值，并且它还允许重复元素。
*   如果`Count`等于`Capacity`，则列表的容量会通过重新分配内部数组而自动增加。在添加新元素之前，现有元素将被复制到新数组中。
*   `List<T>`类通过实现`IList<T>`泛型接口，是`ArrayList`类的泛型等价类。
*   这个类可以同时使用等式和排序比较器。
*   `List<T>`类默认不排序，元素由从零开始的索引访问。
*   对于非常大的`List<T>`对象，您可以通过在运行时环境中将配置元素的`enabled`属性设置为`true`，将64位系统上的最大容量增加到20亿个元素。

### 构造器

| 构造器 | 描述 |
| --- | --- |
| `List<T>()` | 初始化`List<T>`类的新实例，该实例为空并具有默认的初始容量。 |
| `List<T>(IEnumerable<T>)` | 初始化`List<T>`类的新实例，该实例包含从指定集合复制的元素，并且有足够的容量容纳复制的元素数量。 |
| `List<T>(Int32)` | 初始化`List<T>`类的新实例，该实例为空并具有指定的初始容量。 |

**示例:**

```cs
// C# program to create a List<T>
using System;
using System.Collections.Generic;

class Geeks {

// Main Method
    public static void Main(String[] args)
    {

// Creating a List of integers
        List<int> firstlist = new List<int>();

// displaying the number
        // of elements of List<T>
        Console.WriteLine(firstlist.Count);
    }
}
```

**输出:**

```cs

```

### 属性

| 属性 | 描述 |
| --- | --- |
| `Capacity` | 获取或设置内部数据结构在不调整大小的情况下可以容纳的元素总数。 |
| `Count` | 获取`List<T>`中包含的元素数量。 |
| `Item[Int32]` | 获取或设置指定索引处的元素。 |

**示例:**

```cs
// C# program to illustrate the
// Capacity Property of List<T>
using System;
using System.Collections.Generic;

class Geeks {

// Main Method
    public static void Main(String[] args)
    {

// Creating a List of integers
        // Here we are not setting
        // Capacity explicitly
        List<int> firstlist = new List<int>();

// adding elements in firstlist
        firstlist.Add(1);
        firstlist.Add(2);
        firstlist.Add(3);
        firstlist.Add(4);

// Printing the Capacity of firstlist
        Console.WriteLine("Capacity Is: " + firstlist.Capacity);

// Printing the Count of firstlist
        Console.WriteLine("Count Is: " + firstlist.Count);

// Adding some more
        // elements in firstlist
        firstlist.Add(5);
        firstlist.Add(6);

// Printing the Capacity of firstlist
        // It will give output 8 as internally
        // List is resized
        Console.WriteLine("Capacity Is: " + firstlist.Capacity);

// Printing the Count of firstlist
        Console.WriteLine("Count Is: " + firstlist.Count);
    }
}
```

**输出:**

```cs
Capacity Is: 4
Count Is: 4
Capacity Is: 8
Count Is: 6
```

### 方法

| 方法 | 描述 |
| --- | --- |
| `Add(T)` | 将对象添加到`List<T>`的末尾。 |
| `AddRange(IEnumerable<T>)` | 将指定集合的元素添加到`List<T>`的末尾。 |
| `AsReadOnly()` | 返回当前集合的只读`ReadOnlyCollection<T>`包装。 |
| `BinarySearch()` | 使用二分搜索法算法定位排序列表中的特定元素或其一部分。 |
| `Clear()` | 从`List<T>`中移除所有元素。 |
| `Contains(T)` | 确定一个元素是否在`List<T>`中。 |
| `ConvertAll<TOutput>(Converter<T,TOutput>)` | 将当前`List<T>`中的元素转换为另一种类型，并返回包含转换元素的列表。 |
| `CopyTo()` | 将`List<T>`或其一部分复制到数组中。 |
| `Equals(Object)` | 确定指定的对象是否等于当前对象。 |
| `Exists(Predicate<T>)` | 确定`List<T>`是否包含与指定谓词定义的条件相匹配的元素。 |
| `Find(Predicate<T>)` | 搜索与指定谓词定义的条件相匹配的元素，并返回整个列表中的第一个匹配项。 |
| `FindAll(Predicate<T>)` | 检索与指定谓词定义的条件匹配的所有元素。 |
| `FindIndex(Predicate<T>)` | 搜索与指定谓词定义的条件相匹配的元素，并返回列表中第一个匹配项的从零开始的索引或其一部分。如果找不到符合条件的项目，这个方法会传回-1。 |
| `FindLast(Predicate<T>)` | 搜索与指定谓词定义的条件相匹配的元素，并返回整个`List<T>`中的最后一个匹配项。 |
| `FindLastIndex(Predicate<T>)` | 搜索与指定谓词定义的条件相匹配的元素，并返回列表中最后一次出现的从零开始的索引或其一部分。 |
| `ForEach(Action<T>)` | 对`List<T>`中的每个元素执行指定的操作。 |
| `GetEnumerator()` | 返回遍历`List<T>`的枚举数。 |
| `GetHashCode()` | 用作默认哈希函数。 |
| `GetRange(Int32, Int32)` | 在源`List<T>`中创建一系列元素的浅拷贝。 |
| `GetType()` | 获取当前实例的类型。 |
| `IndexOf(T)` | 返回`List<T>`或其一部分中第一个值的从零开始的索引。 |
| `Insert(Int32, T)` | 在`List<T>`中指定的索引处插入一个元素。 |
| `InsertRange(Int32, IEnumerable<T>)` | 将集合的元素插入`List<T>`中指定索引处。 |
| `LastIndexOf(T)` | 返回`List<T>`中某个值最后一次出现的从零开始的索引或其一部分。 |
| `MemberwiseClone()` | 创建当前对象的浅拷贝。 |
| `Remove(T)` | 从`List<T>`中删除特定对象的第一次出现。 |
| `RemoveAll(Predicate<T>)` | 移除与指定谓词定义的条件匹配的所有元素。 |
| `RemoveAt(Int32)` | 移除`List<T>`指定索引处的元素。 |
| `RemoveRange(Int32, Int32)` | 从`List<T>`中删除一系列元素。 |
| `Reverse()` | 颠倒`List<T>`或其一部分中元素的顺序。 |
| `Sort()` | 使用指定或默认的`IComparer<T>`实现或提供的比较委托来比较列表元素，对`List<T>`中的元素或部分元素进行排序。 |
| `ToArray()` | 将`List<T>`的元素复制到新数组中。 |
| `ToString()` | 返回表示当前对象的字符串。 |
| `TrimExcess()` | 如果`List<T>`中元素的实际数量小于阈值，则将容量设置为该数量。 |
| `TrueForAll(Predicate<T>)` | 确定`List<T>`中的每个元素是否符合指定谓词定义的条件。 |

**例 1:**

```cs
// C# Program to check whether the
// element is present in the List
// or not
using System;
using System.Collections.Generic;

class Geeks {

// Main Method
    public static void Main(String[] args)
    {

// Creating an List<T> of Integers
        List<int> firstlist = new List<int>();

// Adding elements to List
        firstlist.Add(1);
        firstlist.Add(2);
        firstlist.Add(3);
        firstlist.Add(4);
        firstlist.Add(5);
        firstlist.Add(6);
        firstlist.Add(7);

// Checking whether 4 is present
        // in List or not
        Console.Write(firstlist.Contains(4));
    }
}
```

**输出:**

```cs
True
```

**例 2:**

```cs
// C# Program to remove the element at
// the specified index of the List<T>
using System;
using System.Collections.Generic;

class Geeks {

// Main Method
    public static void Main(String[] args)
    {

// Creating an List<T> of Integers
        List<int> firstlist = new List<int>();

// Adding elements to List
        firstlist.Add(17);
        firstlist.Add(19);
        firstlist.Add(21);
        firstlist.Add(9);
        firstlist.Add(75);
        firstlist.Add(19);
        firstlist.Add(73);

Console.WriteLine("Elements Present in List:\n");

int p = 0;

// Displaying the elements of List
        foreach(int k in firstlist)
        {
            Console.Write("At Position {0}: ", p);
            Console.WriteLine(k);
            p++;
        }

Console.WriteLine(" ");

// removing the element at index 3
        Console.WriteLine("Removing the element at index 3\n");

// 9 will remove from the List
        // and 75 will come at index 3
        firstlist.RemoveAt(3);

int p1 = 0;

// Displaying the elements of List
        foreach(int n in firstlist)
        {
            Console.Write("At Position {0}: ", p1);
            Console.WriteLine(n);
            p1++;
        }
    }
}
```

**输出:**

```cs
Elements Present in List:

At Position 0: 17
At Position 1: 19
At Position 2: 21
At Position 3: 9
At Position 4: 75
At Position 5: 19
At Position 6: 73

Removing the element at index 3

At Position 0: 17
At Position 1: 19
At Position 2: 21
At Position 3: 75
At Position 4: 19
At Position 5: 73
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1?view=netframework-4.7.2)