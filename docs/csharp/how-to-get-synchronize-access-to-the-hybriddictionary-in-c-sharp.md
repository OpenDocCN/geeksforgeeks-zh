# 如何在 C# 中同步访问混合字典

> 原文:[https://www . geesforgeks . org/如何同步访问 c-sharp 中的混合词典/](https://www.geeksforgeeks.org/how-to-get-synchronize-access-to-the-hybriddictionary-in-c-sharp/)

**杂交词典。同步根属性**用于获取一个对象，该对象可用于同步访问[混合字典](https://www.geeksforgeeks.org/c-sharp-hybriddictionary-class/)。它实现了一个链表和哈希表数据结构。当集合很小时，它通过使用列表字典来实现 IDictionary，当集合很大时，它通过使用哈希表来实现 IDictionary。

> **语法:**公共虚拟对象 SyncRoot { get}
> 
> **属性值:**可用于同步访问混合字典的对象。

**要点:**

*   完成对象同步后，只有一个线程可以操作混合字典中的数据。
*   属性是提供读取、写入和计算私有数据字段的方法的类的成员。
*   同步代码不能直接在集合上执行，因此它必须在集合的同步根上执行操作，以保证从其他对象派生的集合的正确操作。
*   检索该属性的值是一个 O(1)操作。

以下程序说明了上述属性的使用:

**示例 1:** 在这段代码中，我们使用 SyncRoot 获得名为 *hd* 的混合字典的 Synchronized 访问，这不是一个线程安全的过程，可能会导致异常。所以为了避免异常，我们在枚举期间锁定集合。

```cs
// C# program to illustrate the
// use of SyncRoot property of
// the HybridDictionary class
using System;
using System.Threading;
using System.Collections;
using System.Collections.Specialized;

namespace sync_root {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Declaring an HybridDictionary
        HybridDictionary hd = new HybridDictionary();

        // Adding elements to HybridDictionary
        hd.Add("1", "HTML");
        hd.Add("2", "CSS");
        hd.Add("3", "PHP");
        hd.Add("4", "JQuery");
        hd.Add("5", "JavaScript");

        // Using the SyncRoot property
        lock(hd.SyncRoot)
        {
            // foreach loop to display
            // the elements in hd
            foreach(DictionaryEntry i in hd)
                Console.WriteLine(i.Key + " ---- " + i.Value);
        }
    }
}
}
```

**Output:**

```cs
1 ---- HTML
2 ---- CSS
3 ---- PHP
4 ---- JQuery
5 ---- JavaScript

```

**例 2:**

```cs
// C# program to illustrate the
// use of SyncRoot property of
// the HybridDictionary class
using System;
using System.Threading;
using System.Collections;
using System.Collections.Specialized;

namespace sync_root {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Declaring an HybridDictionary
        HybridDictionary hd= new HybridDictionary();

        // Adding elements to HybridDictionary
        hd.Add("10", "Shyam");
        hd.Add("20", "Ram");
        hd.Add("30", "Rohit");
        hd.Add("40", "Sohan");
        hd.Add("50", "Rohan");

        // Using the SyncRoot property
        lock(hd.SyncRoot)
        {
            // foreach loop to display
            // the elements in hd
            foreach(DictionaryEntry i in hd)
                Console.WriteLine(i.Key + " ----> " + i.Value);
        }
    }
}
}
```

**Output:**

```cs
10 ----> Shyam
20 ----> Ram
30 ----> Rohit
40 ----> Sohan
50 ----> Rohan

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . hybrid dictionary . sync root？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.hybriddictionary.syncroot?view=netframework-4.7.2)