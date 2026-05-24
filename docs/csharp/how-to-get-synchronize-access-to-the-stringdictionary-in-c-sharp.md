# 如何在 C# 中同步访问字符串列表

> 原文:[https://www . geeksforgeeks . org/如何同步访问 c-sharp 中的 stringdictionary/](https://www.geeksforgeeks.org/how-to-get-synchronize-access-to-the-stringdictionary-in-c-sharp/)

**StringDictionary。同步根属性**用于获取一个对象，该对象可用于同步对[字符串的访问](https://www.geeksforgeeks.org/c-sharp-stringdictionary-class/)。它只允许字符串键和字符串值。它存在性能问题。它实现了一个哈希表，其中键和值被强类型化为字符串而不是对象。

> **语法:**公共虚拟对象 SyncRoot { get}
> 
> **属性值:**一个对象，可用于同步对字符串的访问。

**要点:**

*   完成对象的同步后，只有一个线程可以操作 StringDictionary 中的数据。
*   属性是提供读取、写入和计算私有数据字段的方法的类的成员。
*   同步代码不能直接在集合上执行，因此它必须在集合的同步根上执行操作，以保证从其他对象派生的集合的正确操作。
*   检索该属性的值是一个 O(1)操作。

以下程序说明了上述属性的使用:

**示例 1:** 在这段代码中，我们使用 SyncRoot 来获得对名为 *sd* 的 StringDictionary 的同步访问，这不是一个线程安全的过程，可能会导致异常。所以为了避免异常，我们在枚举期间锁定集合。

```cs
// C# program to illustrate the
// use of SyncRoot property of
// the StringDictionary class
using System;
using System.Threading;
using System.Collections;
using System.Collections.Specialized; 

namespace sync_root {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Declaring an StringDictionary
        StringDictionary sd = new StringDictionary();

        // Adding elements to StringDictionary
        sd.Add("Australia", "Canberra"); 
        sd.Add("Belgium", "Brussels"); 
        sd.Add("Netherlands", "Amsterdam"); 
        sd.Add("China", "Beijing"); 
        sd.Add("Russia", "Moscow"); 
        sd.Add("India", "New Delhi"); 

        // Using the SyncRoot property
        lock(sd.SyncRoot)
        {
            // foreach loop to display
            // the elements in sd
            foreach(DictionaryEntry i in sd) 
                Console.WriteLine(i.Key + " ---- " + i.Value);
        }
    }
}
}
```

**Output:**

```cs
china ---- Beijing
netherlands ---- Amsterdam
belgium ---- Brussels
australia ---- Canberra
india ---- New Delhi
russia ---- Moscow

```

**例 2:**

```cs
// C# program to illustrate the
// use of SyncRoot property of
// the StringDictionary class
using System;
using System.Threading;
using System.Collections;
using System.Collections.Specialized; 

namespace sync_root {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Declaring an StringDictionary
        StringDictionary sd = new StringDictionary();

        // Adding elements to StringDictionary
        sd.Add("1", "C"); 
        sd.Add("2", "C++"); 
        sd.Add("3", "Java"); 
        sd.Add("4", "C#"); 
        sd.Add("5", "HTML"); 

        // Using the SyncRoot property
        lock(sd.SyncRoot)
        {
            // foreach loop to display
            // the elements in sd
            foreach(DictionaryEntry i in sd) 
                Console.WriteLine(i.Key + " ----> " + i.Value);
        }
    }
}
}
```

**Output:**

```cs
3 ----> Java
5 ----> HTML
4 ----> C#
2 ----> C++
1 ----> C

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string dictionary . sync root？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringdictionary.syncroot?view=netframework-4.7.2)