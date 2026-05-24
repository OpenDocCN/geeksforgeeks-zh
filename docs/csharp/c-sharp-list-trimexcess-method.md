# C# |列表。三重排除法

> 原文:[https://www . geeksforgeeks . org/c-sharp-list-trimexcess-method/](https://www.geeksforgeeks.org/c-sharp-list-trimexcess-method/)

***列表< T >。TrimExcess*** 方法用于将容量设置为列表< T >中元素的实际数量，如果该数量小于阈值。

**语法:**

```cs
public void TrimExcess ();
```

**注:**

*   如果没有新元素添加到集合中，此方法可用于最小化集合的内存开销。
*   要将列表<t>重置为初始状态，请在调用 TrimExcess 方法之前调用 Clear 方法。</t>
*   修剪空列表<t>将列表<t>的容量设置为默认容量。</t></t>
*   然而，重新分配和复制一个大列表<t>的成本可能相当大，所以如果列表超过 90%的容量，TrimExcess 方法什么也不做。这避免了为了相对较小的收益而导致较大的重新分配成本。</t>
*   这个方法是一个 O(n)运算，其中 n 是 Count。

以下程序说明了**列表< T >的使用。三阶段**方法:

**例 1:**

```cs
// C# code to set the capacity to the
// actual number of elements in the List
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a List of strings
        List<string> mylist = new List<string>();

        // Inserting elements into List
        mylist.Add("1");
        mylist.Add("2");
        mylist.Add("3");
        mylist.Add("4");
        mylist.Add("5");

        // To  display the capacity of list
        Console.WriteLine(mylist.Capacity);

        // To display number of elements in List
        Console.WriteLine(mylist.Count);

        // using TrimExcess method
        mylist.TrimExcess();

        // To  display the capacity of list
        Console.WriteLine(mylist.Capacity);

        // To display number of elements in List
        Console.WriteLine(mylist.Count);
    }
}
```

**输出:**

```cs
8
5
5
5

```

**例 2:**

```cs
// C# code to set the capacity to the
// actual number of elements in the List
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a List of integers
        List<int> mylist = new List<int>();

        // Inserting elements into List
        mylist.Add(45);
        mylist.Add(78);
        mylist.Add(32);
        mylist.Add(231);
        mylist.Add(123);
        mylist.Add(76);
        mylist.Add(726);
        mylist.Add(716);
        mylist.Add(876);

        // To  display the capacity of list
        Console.WriteLine(mylist.Capacity);

        // To display number of elements in List
        Console.WriteLine(mylist.Count);

        // using TrimExcess method
        mylist.TrimExcess();

        // To  display the capacity of list
        Console.WriteLine(mylist.Capacity);

        // To display number of elements in List
        Console.WriteLine(mylist.Count);

        // using clear method
        mylist.Clear();

        // To  display the capacity of list
        Console.WriteLine(mylist.Capacity);

        // To display number of elements in List
        Console.WriteLine(mylist.Count);
    }
}
```

**输出:**

```cs
16
9
9
9
9
0

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . tri excess？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.trimexcess?view=netframework-4.7.2)