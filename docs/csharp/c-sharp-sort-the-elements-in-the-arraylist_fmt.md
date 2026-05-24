# C# | 对数组列表中的元素进行排序

> 原文：[https://www.geeksforgeeks.org/c-sharp-sort-the-elements-in-the-arraylist/](https://www.geeksforgeeks.org/c-sharp-sort-the-elements-in-the-arraylist/)

**`ArrayList.Sort` 方法**用于对数组列表中的元素进行排序。该方法的重载列表中总共有 3 种方法，如下所示：

1.  `Sort()`
2.  `Sort(IComparer)`
3.  `Sort(Int32, Int32, IComparer)`

## `Sort()`

此方法用于对整个数组列表中的元素进行排序。它使用[**快速排序算法**](https://www.geeksforgeeks.org/quick-sort/)对数组列表的元素进行排序。

**注意：** 这个方法是一个 O(n log n) 运算，其中 n 是 `Count`，在最坏的情况下，它是一个 O(n^2) 运算。

**语法：**

```cs
public virtual void Sort ();
```

**异常：** 如果数组列表是只读的，这个方法将给出 `NotSupportedException`。

**示例：**

```cs
// C# program to illustrate Sort() Method
using System;
using System.Collections;

class GFG {

    // Main method
    public static void Main()
    {

        // create and initialize new ArrayList
        ArrayList mylist = new ArrayList();
        mylist.Add("Welcome");
        mylist.Add("to");
        mylist.Add("Geeks");
        mylist.Add("for");
        mylist.Add("Geeks");
        mylist.Add("2");

        // ArrayList before sorting
        Console.WriteLine("ArrayList before sort:");
        foreach(string i in mylist)
        {
            Console.WriteLine(i);
        }
        Console.WriteLine();

        Console.WriteLine("ArrayList after sort:");

        // sort the ArrayList
        // using Sort() method
        mylist.Sort();

        // ArrayList after sort
        foreach(string i in mylist)
        {
            Console.WriteLine(i);
        }
    }
}
```

**输出：**

```cs
ArrayList before sort:
Welcome
to
Geeks
for
Geeks
2

ArrayList after sort:
2
for
Geeks
Geeks
to
Welcome
```

## `Sort(IComparer)`

此方法用于使用指定的比较器对整个数组列表中的元素进行排序。这个方法是一个 O(n log n) 运算，其中 n 是 `Count`，在最坏的情况下，这是一次 O(n^2) 运算。

**语法：**

```cs
public virtual void Sort (IComparer comparer);
```

这里，在比较元素时使用了 `IComparer` 实现。

**异常：**

*   `NotSupportedException`：如果数组列表是只读的。
*   `InvalidOperationException`：由于比较两个元素时出错。
*   `ArgumentException`：如果为 `comparer` 传递了空值，并且列表中的元素没有实现 `IComparable`。

**示例：**

```cs
// C# program to illustrate Sort(IComparer) Method
using System;
using System.Collections;

class GFG {

    // Calls CaseInsensitiveComparer.Compare
    // with the parameters reversed.
    public class myClass : IComparer {

        int IComparer.Compare(Object a, Object b)
        {
            return ((new CaseInsensitiveComparer()).Compare(b, a));
        }
    }

    // Main method
    public static void Main()
    {

        // create and initialize new ArrayList, i.e. mylist
        ArrayList mylist = new ArrayList();
        mylist.Add("Welcome");
        mylist.Add("to");
        mylist.Add("geeks");
        mylist.Add("for");
        mylist.Add("geeks");
        mylist.Add("2");

        IComparer Comp1 = new myClass();

        // sort the value of ArrayList
        // using Sort(IComparer) method
        mylist.Sort(Comp1);

        foreach(Object ob in mylist)
        {
            Console.WriteLine(ob);
        }
    }
}
```

**输出：**

```cs
Welcome
to
geeks
geeks
for
2
```

## `Sort(Int32, Int32, IComparer)`

此方法用于使用指定的比较器对数组列表中某个元素范围内的元素进行排序。

**注意：** 这个方法是一个 O(n log n) 运算，其中 n 是 `Count`，在最坏的情况下，它是一个 O(n^2) 运算。

**语法：**

```cs
public virtual void Sort (int index, int count, IComparer comparer);
```

**参数：**

*   `index`：是要排序范围的从零开始的索引，该参数的类型为 `System.Int32`。
*   `count`：统计要排序范围的长度，该参数的类型为 `System.Int32`。
*   `comparer`：它是在元素比较期间使用的 `IComparer` 实现。

**异常：**

*   `NotSupportedException`：如果数组列表是只读的。
*   `InvalidOperationException`：由于比较两个元素时出错。
*   `ArgumentException`：如果 `index` 和 `count` 没有在数组列表中指定有效范围。
*   `ArgumentOutOfRangeException`：如果 `index` 小于零。

**示例：**

```cs
// C# program to illustrate the use of
// Sort(Int32, Int32, IComparer) Method
using System;
using System.Collections;

class GFG {

    // Main method
    public static void Main()
    {

        // create and initialize new ArrayList
        ArrayList mylist = new ArrayList();
        mylist.Add("Welcome");
        mylist.Add("to");
        mylist.Add("geeks");
        mylist.Add("for");
        mylist.Add("GFG");
        mylist.Add("2");

        // sort the value of ArrayList from 0 to 4
        // using Sort( Int32, Int32, IComparer) method
        // here the value of IComparer is null
        mylist.Sort(0, 4, null);

        // Display the sorted string
        foreach(string ob in mylist)
        {
            Console.WriteLine(ob);
        }
    }
}
```

**输出：**

```cs
for
geeks
to
Welcome
GFG
2
```

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.sort?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.sort?view=netframework-4.7.2)