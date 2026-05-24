# C# |检查数组列表是否同步(线程安全)

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-ArrayList-is-synchronized-thread-safe/](https://www.geeksforgeeks.org/c-sharp-check-if-arraylist-is-synchronized-thread-safe/)

**数组列表。IsSynchronized Property** 用于获取一个值，该值指示对 ***[数组列表](https://www.geeksforgeeks.org/c-arraylist-class/)*** 的访问是否同步(线程安全)。

**语法:**

```cs
public virtual bool IsSynchronized { get; }
```

**返回值:**如果对数组列表的访问是同步的(线程安全的)，该属性返回*真*，否则返回*假*。默认为*假*。

以下程序说明了上述属性的使用:

**例 1:**

```cs
// C# code to check if ArrayList
// Is Synchronized or not
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList();

        // Adding elements to ArrayList
        myList.Add("A");
        myList.Add("B");
        myList.Add("C");
        myList.Add("D");
        myList.Add("E");
        myList.Add("F");

        // Creates a synchronized
        // wrapper around the ArrayList
        ArrayList smyList = ArrayList.Synchronized(myList);

        // Displays the synchronization
        // status of both ArrayList
        Console.WriteLine("myList is {0}.", myList.IsSynchronized ?
                               "Synchronized" : "Not Synchronized");

        Console.WriteLine("smyList is {0}.", smyList.IsSynchronized ? 
                                "Synchronized" : "Not Synchronized");
    }
}
```

**Output:**

```cs
myList is Not Synchronized.
smyList is Synchronized.

```

**例 2:**

```cs
// C# code to check if ArrayList
// Is Synchronized or not
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList();

        // Adding elements to ArrayList
        myList.Add(1);
        myList.Add(2);
        myList.Add(3);
        myList.Add(4);
        myList.Add(5);
        myList.Add(5);

        // the default is false for 
        // IsSynchronized property
        Console.WriteLine(myList.IsSynchronized);
    }
}
```

**Output:**

```cs
False

```

**注:**

*   检索该属性的值是一个 O(1)操作。
*   为了保证数组列表的线程安全，所有操作都必须通过 Synchronized 方法返回的包装器来完成。
*   枚举集合本质上不是线程安全的过程。即使同步了集合，其他线程仍然可以修改集合，这将导致枚举数引发异常。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . is synchronized？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.issynchronized?view=netframework-4.7.2)