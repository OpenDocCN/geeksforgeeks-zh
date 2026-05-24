# C# |为 SortedList 对象创建同步(线程安全)包装器

> 原文:[https://www . geeksforgeeks . org/c-sharp-creating-synchronized-thread-safe-wrapper-for-a-sorted list-object/](https://www.geeksforgeeks.org/c-sharp-creating-a-synchronized-thread-safe-wrapper-for-a-sortedlist-object/)

**排序列表。同步(排序列表)方法**用于获取一个[排序列表](https://www.geeksforgeeks.org/c-sortedlist-class/)对象的同步(线程安全)包装。

**语法:**

> 公共静态系统。集合。排序列表已同步(系统。Collections . SortedList

这里，*列表*是要同步的 SortedList 对象的名称。

**异常:**如果*列表*为空，该方法将抛出`ArgumentNullException` 。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to create a synchronized
// (thread-safe) wrapper for a
// SortedList object
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an SortedList
        SortedList mySortedList = new SortedList();

        // Adding elements to SortedList
        mySortedList.Add("1", "one");
        mySortedList.Add("2", "two");
        mySortedList.Add("3", "three");
        mySortedList.Add("4", "four");
        mySortedList.Add("5", "five");

        // Creating a synchronized wrapper
        // around the SortedList.
        SortedList mySortedList_1 = 
            SortedList.Synchronized(mySortedList);

        // --------- Using IsSynchronized Property

        // print the status of both SortedList
        Console.WriteLine("mySortedList SortedList is {0}.",
              mySortedList.IsSynchronized ? "synchronized" : 
                                         "not synchronized");

        Console.WriteLine("mySortedList_1 SortedList is {0}.",
              mySortedList_1.IsSynchronized ? "synchronized" : 
                                          "not synchronized");
    }
}
```

**输出:**

```cs
mySortedList SortedList is not synchronized.
mySortedList_1 SortedList is synchronized.

```

**例 2:**

```cs
// C# code to create a synchronized
// (thread-safe) wrapper for a
// SortedList object
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an SortedList
        SortedList mySortedList = new SortedList();

        // Adding elements in SortedList 
        mylist.Add("4", "Even"); 
        mylist.Add("9", "Odd"); 
        mylist.Add("5", "Odd and Prime"); 
        mylist.Add("2", "Even and Prime"); 

        // it will give runtime error as
        // table parameter can't be null
        SortedList my2 = SortedList.Synchronized(null);
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentNullException:值不能为空。
> 参数名称:列表

**注意:**为了[排序列表](https://www.geeksforgeeks.org/c-sortedlist-class/)对象的线程安全，所有操作只能通过这个包装器完成。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . sorted list . synchronized？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist.synchronized?view=netframework-4.7.2)