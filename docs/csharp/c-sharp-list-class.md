# C# |列表类

> 原文:[https://www.geeksforgeeks.org/c-sharp-list-class/](https://www.geeksforgeeks.org/c-sharp-list-class/)

**列表< T >类**代表可以通过索引访问的对象列表。它属于**体系。集合.泛型**命名空间。List 类可以用来创建不同类型的集合，如整数、字符串等。列表< T >类还提供了搜索、排序和操作列表的方法。

**特征:**

*   它不同于数组。A **列表< T >可以动态调整大小**但是数组不能。
*   List <t>类可以接受 null 作为引用类型的有效值，并且它还允许重复元素。</t>
*   如果计数等于容量，则列表的容量会通过重新分配内部阵列而自动增加。在添加新元素之前，现有元素将被复制到新数组中。
*   List <t>类通过实现 IList <t>泛型接口，是数组列表类的泛型等价类。</t></t>
*   这个类可以同时使用等式和排序比较器。
*   列表<t>类默认不排序，元素由从零开始的索引访问。</t>
*   对于非常大的列表<t>对象，您可以通过在运行时环境中将配置元素的 enabled 属性设置为 true，将 64 位系统上的**最大容量增加到 20 亿个元素**。</t>

#### 构造器

| 构造器 | 描述 |
| --- | --- |
| **列表< T > ()** | 初始化列表<t>类的新实例，该实例为空并具有默认的初始容量。</t> |
| --- | --- |
| **列表< T >(无限量< T > )** | 初始化 List <t>类的新实例，该实例包含从指定集合复制的元素，并且有足够的容量容纳复制的元素数量。</t> |
| --- | --- |
| **列表< T > (Int32)** | 初始化列表<t>类的新实例，该实例为空并具有指定的初始容量。</t> |
| --- | --- |

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
0

```

#### 性能

| 财产 | 描述 |
| --- | --- |
| **[运力](https://www.geeksforgeeks.org/c-capacity-of-a-list/)** | 获取或设置内部数据结构在不调整大小的情况下可以容纳的元素总数。 |
| --- | --- |
| **[计数](https://www.geeksforgeeks.org/c-count-the-total-number-of-elements-in-the-list/)** | 获取列表<t>中包含的元素数量。</t> |
| --- | --- |
| **[项【国际 32】](https://www.geeksforgeeks.org/c-gets-or-sets-the-element-at-the-specified-index-in-the-list/)** | 获取或设置指定索引处的元素。 |
| --- | --- |

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

#### 方法

| 方法 | 描述 |
| --- | --- |
| **[加(T)](https://www.geeksforgeeks.org/c-adding-an-element-to-the-list/)** | 将对象添加到列表的末尾<t>。</t> |
| --- | --- |
| **[AddRange(无数<>)](https://www.geeksforgeeks.org/c-adding-the-elements-of-the-specified-collection-to-the-end-of-the-list/)** | 将指定集合的元素添加到列表的末尾<t>。</t> |
| --- | --- |
| **[【ASR only()](https://www.geeksforgeeks.org/c-creating-a-read-only-wrapper-for-listt/)** | 返回当前集合的只读 ReadOnlyCollection <t>包装。</t> |
| --- | --- |
| **[BinarySearch()](https://www.geeksforgeeks.org/list-binarysearch-method-in-c-sharp/)** | 使用二分搜索法算法定位排序列表<t>中的特定元素或其一部分。</t> |
| --- | --- |
| **[晴()](https://www.geeksforgeeks.org/c-removing-all-the-elements-from-the-list/)** | 从列表中移除所有元素<t>。</t> |
| --- | --- |
| **[包含(T)](https://www.geeksforgeeks.org/c-how-to-check-whether-a-list-contains-a-specified-element/)** | 确定一个元素是否在列表<t>中。</t> |
| --- | --- |
| **转换器(转换器)** | 将当前列表<t>中的元素转换为另一种类型，并返回包含转换元素的列表。</t> |
| --- | --- |
| **CopyTo()** | 将列表<t>或其一部分复制到数组中。</t> |
| --- | --- |
| **[等于(对象)](https://www.geeksforgeeks.org/c-check-if-two-listt-objects-are-equal/)** | 确定指定的对象是否等于当前对象。 |
| --- | --- |
| **[存在(谓语<T>)](https://www.geeksforgeeks.org/c-how-to-check-whether-a-list-contains-the-elements-that-match-the-specified-conditions/)T3】** | 确定列表<t>是否包含与指定谓词定义的条件相匹配的元素。</t> |
| --- | --- |
| **[Find(谓语<T>)](https://www.geeksforgeeks.org/c-sharp-first-occurrence-in-the-list-that-matches-the-specified-conditions/)T3】** | 搜索与指定谓词定义的条件相匹配的元素，并返回整个列表中的第一个匹配项<t>。</t> |
| --- | --- |
| **[FindAll(谓语<T>)](https://www.geeksforgeeks.org/c-how-to-get-all-elements-of-a-list-that-match-the-conditions-specified-by-the-predicate/)T3】** | 检索与指定谓词定义的条件匹配的所有元素。 |
| --- | --- |
| **[【查找指数()](https://www.geeksforgeeks.org/list-findindex-method-in-c-sharp-with-examples/)** | 搜索与指定谓词定义的条件相匹配的元素，并返回列表中第一个匹配项的从零开始的索引<t>或其一部分。如果找不到符合条件的项目，这个方法会传回-1。</t> |
| --- | --- |
| **[FindLast(谓语<T>)](https://www.geeksforgeeks.org/c-sharp-how-to-get-the-last-occurrence-of-the-element-in-the-list-that-match-the-specified-conditions/)T3】** | 搜索与指定谓词定义的条件相匹配的元素，并返回整个列表<t>中的最后一个匹配项。</t> |
| --- | --- |
| **[【find lastindex()](https://www.geeksforgeeks.org/list-findlastindex-method-in-c-sharp-set-1/)** | 搜索与指定谓词定义的条件相匹配的元素，并返回列表中最后一次出现的从零开始的索引<t>或其一部分。</t> |
| --- | --- |
| **[ForEach(动作<T>)](https://www.geeksforgeeks.org/c-how-to-perform-a-specified-action-on-each-element-of-the-list/)T3】** | 对列表中的每个元素执行指定的操作<t>。</t> |
| --- | --- |
| **[【get 分子()](https://www.geeksforgeeks.org/c-get-an-enumerator-that-iterates-through-the-list/)** | 返回遍历列表<t>的枚举数。</t> |
| --- | --- |
| **GetHashCode（）** | 用作默认哈希函数。 |
| --- | --- |
| 抱怨(Int32，Int32) | 在源列表<t>中创建一系列元素的浅拷贝。</t> |
| --- | --- |
| **GetType()** | 获取当前实例的类型。 |
| --- | --- |
| **指数（）** | 返回列表<t>或其一部分中第一个值的从零开始的索引。</t> |
| --- | --- |
| **插入(Int32，T)** | 在列表中指定的索引处插入一个元素<t>。</t> |
| --- | --- |
| **[插入范围(Int32，无数<>)](https://www.geeksforgeeks.org/c-how-to-insert-the-elements-of-a-collection-into-the-list-at-the-specified-index/)** | 将集合的元素插入列表中指定索引处的<t>。</t> |
| --- | --- |
| **最后索引（）** | 返回列表中某个值最后一次出现的从零开始的索引<t>或其一部分。</t> |
| --- | --- |
| **MemberWiseCrone()** | 创建当前对象的浅拷贝。 |
| --- | --- |
| **[移除(T)](https://www.geeksforgeeks.org/c-removing-the-specified-element-from-the-list/)** | 从列表<t>中删除特定对象的第一次出现。</t> |
| --- | --- |
| **[移除所有(谓词<T>)](https://www.geeksforgeeks.org/c-remove-all-elements-of-a-list-that-match-the-conditions-defined-by-the-predicate/)T3】** | 移除与指定谓词定义的条件匹配的所有元素。 |
| --- | --- |
| **[移除 At(Int32)](https://www.geeksforgeeks.org/c-how-to-remove-the-element-from-the-specified-index-of-the-list/)** | 移除列表指定索引处的元素<t>。</t> |
| --- | --- |
| **[移除范围(Int32，Int32)](https://www.geeksforgeeks.org/c-removing-a-range-of-elements-from-the-list/)** | 从列表中删除一系列元素<t>。</t> |
| --- | --- |
| **[【反转()](https://www.geeksforgeeks.org/c-sharp-reverse-the-order-of-the-elements-in-the-entire-list-or-in-the-specified-range/)** | 颠倒列表<t>或其一部分中元素的顺序。</t> |
| --- | --- |
| **[【排序()](https://www.geeksforgeeks.org/how-to-sort-list-in-c-sharp-set-1/)** | 使用指定或默认的 IComparer <t>实现或提供的比较<t>委托来比较列表元素，对列表中的元素或部分元素进行排序。</t></t> |
| --- | --- |
| **toaarray()** | 将列表<t>的元素复制到新数组中。</t> |
| --- | --- |
| **ToString()** | 返回表示当前对象的字符串。 |
| --- | --- |
| **[【quarter xcess()](https://www.geeksforgeeks.org/c-list-trimexcess-method/)** | 如果列表中元素的实际数量小于阈值，则将容量设置为该数量<t>。</t> |
| --- | --- |
| **[TrueForAll(谓语<T>)](https://www.geeksforgeeks.org/c-check-if-every-list-element-matches-the-predicate-conditions/)T3】** | 确定列表<t>中的每个元素是否符合指定谓词定义的条件。</t> |
| --- | --- |

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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1?view=netframework-4.7.2)