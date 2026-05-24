# C# |获取排序列表对象指定索引处的值

> 原文:[https://www . geeksforgeeks . org/c-sharp-按指定的排序索引获取值列表对象/](https://www.geeksforgeeks.org/c-sharp-getting-the-value-at-the-specified-index-of-a-sortedlist-object/)

**排序列表。GetByIndex(Int32)方法**用于获取 SortedList 对象的指定索引处的值。

**语法:**

```cs
public virtual object GetByIndex (int index);
```

这里*索引*是要获取的值的从零开始的索引。

**返回值:**返回 SortedList 对象指定索引处的值。

**异常:**如果*索引*在 SortedList 对象的有效索引范围之外，此方法将抛出`ArgumentOutOfRangeException` 。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to get the value at the specified
// index of a SortedList object.
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a SortedList of integers
        SortedList mylist = new SortedList();

        // Adding elements to SortedList
        mylist.Add("1", "C++");
        mylist.Add("2", "Java");
        mylist.Add("3", "DSA");
        mylist.Add("4", "Python");
        mylist.Add("5", "C#");

        // getting the indexing and
        // store into a variable
        int i = 4;

        // getting the value at index 4
        Console.WriteLine("Value at index {0} is {1}",
                          i, mylist.GetByIndex(i));
    }
}
```

**输出:**

```cs
Value at index 4 is C#

```

**例 2:**

```cs
// C# code to get the value at the specified
// index of a SortedList object.
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a SortedList of integers
        SortedList mylist = new SortedList();

        // Adding elements to SortedList
        mylist.Add("First", "Ram");
        mylist.Add("Second", "Shyam");
        mylist.Add("Third", "Mohit");
        mylist.Add("Fourth", "Rohit");
        mylist.Add("Fifth", "Manish");

        // getting the indexing and
        // store into a variable
        // it will give error as
        // index is out of range
        int i = 7;

        // getting the value at index 7
        Console.WriteLine("Value at index {0} is {1}",
                          i, mylist.GetByIndex(i));
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:索引超出范围。必须是非负的，并且小于集合的大小。
> 参数名称:索引

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . getby index？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.getbyindex?view=netframework-4.7.2)