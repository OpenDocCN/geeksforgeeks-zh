# C# |为哈希表创建同步(线程安全)包装器

> 原文:[https://www . geeksforgeeks . org/c-sharp-creating-synchronized-thread-safe-wrapper-for-hashtable/](https://www.geeksforgeeks.org/c-sharp-creating-a-synchronized-thread-safe-wrapper-for-the-hashtable/)

**哈希表。同步(哈希表)方法**用于为[哈希表](https://www.geeksforgeeks.org/c-hashtable-class/)返回一个同步(线程安全)包装器。
**语法:**

> 公共静态系统。集合。哈希表同步(系统。Collections.Hashtable 表)；

这里*表*是要同步的哈希表。
**返回值:**这个方法为哈希表返回一个同步的(线程安全的)包装。
**异常:**如果*表*为空，该方法将抛出 *ArgumentNullException* 。
以下程序说明了上述方法的使用:
**示例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# code to get a synchronized (thread-
// safe) wrapper for the Hashtable
using System;
using System.Collections;

class GFG {

    // Main method
    static void Main(string[] args)
    {

        // create and initialize Hash table
        // using Add() method
        Hashtable has1 = new Hashtable();
        has1.Add("1", "Welcome");
        has1.Add("2", "to");
        has1.Add("3", "geeks");
        has1.Add("4", "for");
        has1.Add("5", "geeks");

        // Creating a synchronized packing
        // around the Hashtable
        Hashtable has2 = Hashtable.Synchronized(has1);

        // --------- Using IsSynchronized Property

        // print the status of both Hashtables
        Console.WriteLine("has1 Hashtable is {0}.",
            has1.IsSynchronized ? "synchronized" :
                              "not synchronized");

        Console.WriteLine("has2 Hashtable is {0}.",
             has2.IsSynchronized ? "synchronized" :
                               "not synchronized");
    }
}
```

**输出:**

```cs
has1 Hashtable is not synchronized.
has2 Hashtable is synchronized.
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# code to get a synchronized (thread-
// safe) wrapper for the Hashtable
using System;
using System.Collections;

class GFG {

    // Main method
    static void Main(string[] args)
    {

        // create and initialize Hash table
        // there will be no elements
        Hashtable has1 = new Hashtable();

        // it will give runtime error as
        // table parameter can't be null
        Hashtable has2 = Hashtable.Synchronized(null);
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentNullException:值不能为空。
> 参数名称:表

**注:**

*   这个方法对于多个读者和作者来说是线程安全的。此外，同步包装确保一次只有一个编写器写入。
*   枚举集合本质上不是一个线程安全的过程。其他线程仍然可以修改集合，这将导致枚举数引发异常，即使集合是同步的。
*   为了保证枚举期间的线程安全，可以在整个枚举期间锁定集合，也可以捕获由其他线程所做的更改导致的异常。
*   这个方法是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . hashtable . synchronized？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.synchronized?view=netframework-4.7.2)