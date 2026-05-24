# C# |如何同步访问数组列表

> 原文:[https://www . geeksforgeeks . org/c-sharp-如何同步访问数组列表/](https://www.geeksforgeeks.org/c-sharp-how-to-get-synchronize-access-to-the-arraylist/)

**数组列表。同步根属性**用于获取一个对象，该对象可用于同步对数组列表的访问。[数组列表](https://www.geeksforgeeks.org/arraylist-in-c-sharp/)表示可以单独索引的对象的有序集合。它基本上是[阵](https://www.geeksforgeeks.org/c-sharp-arrays/)的替代品。它还允许动态内存分配、添加、搜索和排序列表中的项目。

**要点:**

*   完成对象的同步后，只有一个线程可以操作数组列表中的数据。
*   属性是提供读取、写入和计算私有数据字段的方法的类的成员。
*   同步代码不能直接在集合上执行，因此它必须在集合的同步根上执行操作，以保证从其他对象派生的集合的正确操作。
*   检索该属性的值是一个 O(1)操作。

> **语法:**公共虚拟对象 SyncRoot { get}
> 
> **属性值:**可用于同步访问数组列表的对象。

**示例 1:** 在这段代码中，我们使用 SyncRoot 来获得名为 *arrlist* 的 ArrayList 的 Synchronized 访问，这不是一个线程安全的过程，可能会导致异常。所以为了避免异常，我们锁定集合。

```cs
// C# program to illustrate the
// use of SyncRoot property of
// the ArrayList
using System;
using System.Threading;
using System.Collections;

namespace sync_root {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Declaring an ArrayList
        ArrayList arrlist = new ArrayList();

        // Adding elements to ArrayList
        arrlist.Add(1);
        arrlist.Add(2);
        arrlist.Add(3);
        arrlist.Add(4);
        arrlist.Add(5);

        // Using the SyncRoot property
        lock(arrlist.SyncRoot)
        {
            // foreach loop to display
            // the elements in arrlist
            foreach(Object i in arrlist)
                Console.WriteLine(i);
        }
    }
}
}
```

**Output:**

```cs
1
2
3
4
5

```

**例 2:**

```cs
// C# program to illustrate the
// use of SyncRoot property of
// the ArrayList
using System;
using System.Threading;
using System.Collections;

namespace sync_root {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Declaring an ArrayList
        ArrayList arrlist = new ArrayList();

        // Adding elements to ArrayList
        arrlist.Add("C");
        arrlist.Add("C++");
        arrlist.Add("Java");
        arrlist.Add("C#");
        arrlist.Add("HTML");

        // Using the SyncRoot property
        lock(arrlist.SyncRoot)
        {
            // foreach loop to display
            // the elements in arrlist
            foreach(Object i in arrlist)
                Console.WriteLine(i);
        }
    }
}
}
```

**Output:**

```cs
C
C++
Java
C#
HTML

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . sync root？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.syncroot?view=netframework-4.7.2)