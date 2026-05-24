# C# |为数组列表创建同步(线程安全)包装器

> 原文:[https://www . geeksforgeeks . org/c-sharp-creating-synchronized-thread-safe-wrapper-for-the-ArrayList/](https://www.geeksforgeeks.org/c-sharp-creating-a-synchronized-thread-safe-wrapper-for-the-arraylist/)

**Synchronized(ArrayList)** 方法用于获取一个同步的 [ArrayList](https://www.geeksforgeeks.org/c-arraylist-class/) 包装器(线程安全)。

**语法:**

> 公共静态系统。集合。数组列表同步(系统。Collections.ArrayList 列表)；

这里*列表*是要同步的[数组列表](https://www.geeksforgeeks.org/c-arraylist-class/)。

**返回值:**返回一个同步的数组列表包装器(线程安全)。

**异常:**如果*列表*为空，该方法抛出*参数为空异常*。

以下程序说明了上述方法的使用:

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
        myList.Add("Geeks");
        myList.Add("for");
        myList.Add("Geeks");
        myList.Add("Noida");
        myList.Add("Geeks Classes");
        myList.Add("Delhi");

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

**输出:**

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
        myList.Add("Geeks");
        myList.Add("for");
        myList.Add("Geeks");
        myList.Add("Noida");
        myList.Add("Geeks Classes");
        myList.Add("Delhi");

        // it will give error as
        // the parameter is null
        ArrayList smyList = ArrayList.Synchronized(null);
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentNullException:值不能为空。
> 参数名称:列表

**注意:**为了[数组列表](https://www.geeksforgeeks.org/c-arraylist-class/)的线程安全，所有操作都必须通过这个包装器完成。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . synchronized？view = net framework-4 . 7 . 2 # System _ Collections _ ArrayList _ Synchronized _ System _ Collections _ ArrayList _](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.synchronized?view=netframework-4.7.2# System_Collections_ArrayList_Synchronized_System_Collections_ArrayList_)