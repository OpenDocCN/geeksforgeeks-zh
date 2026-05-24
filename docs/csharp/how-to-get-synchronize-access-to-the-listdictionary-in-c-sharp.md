# 如何在 C# 中同步访问列表字典

> 原文:[https://www . geesforgeks . org/如何同步访问 c-sharp 中的 list dictionary/](https://www.geeksforgeeks.org/how-to-get-synchronize-access-to-the-listdictionary-in-c-sharp/)

**列表词典。同步根属性**用于获取一个对象，该对象可用于同步对列表字典的访问。[列表词典](https://www.geeksforgeeks.org/c-sharp-listdictionary-class/)是一个专门的集合。它属于系统。集合。专用命名空间。此类型表示非泛型字典类型。它是用链表实现的。

> **语法:**公共虚拟对象 SyncRoot { get}
> 
> **属性值:**可用于同步访问列表字典的对象。

**要点:**

*   完成对象的同步后，只有一个线程可以操作列表字典中的数据。
*   属性是提供读取、写入和计算私有数据字段的方法的类的成员。
*   同步代码不能直接在集合上执行，因此它必须在集合的同步根上执行操作，以保证从其他对象派生的集合的正确操作。
*   检索该属性的值是一个 O(1)操作。

以下程序说明了上述属性的使用:

**示例 1:** 在这段代码中，我们使用 SyncRoot 来获得名为*lisdict*的 listdict 的 Synchronized 访问，这不是一个线程安全的过程，可能会导致异常。所以为了避免异常，我们在枚举期间锁定集合。

```cs
// C# program to illustrate the
// use of SyncRoot property of
// the ListDictionary class
using System;
using System.Threading;
using System.Collections;
using System.Collections.Specialized;

namespace sync_root {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Declaring an ListDictionary
        ListDictionary listdict = new ListDictionary();

        // Adding elements to ListDictionary
        listdict.Add("10", "JQUERY");
        listdict.Add("20", "HTML");
        listdict.Add("30", "CSS");
        listdict.Add("40", "C");
        listdict.Add("50", "C++");
        listdict.Add("60", "C#");

        // Using the SyncRoot property
        lock(listdict.SyncRoot)
        {
            // foreach loop to display
            // the elements in listdict
            foreach(DictionaryEntry i in listdict)
                Console.WriteLine(i.Key + " ---- " + i.Value);
        }
    }
}
}
```

**Output:**

```cs
10 ---- JQUERY
20 ---- HTML
30 ---- CSS
40 ---- C
50 ---- C++
60 ---- C#

```

**例 2:**

```cs
// C# program to illustrate the
// use of SyncRoot property of
// the ListDictionary class
using System;
using System.Threading;
using System.Collections;
using System.Collections.Specialized;

namespace sync_root {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Declaring an ListDictionary
        ListDictionary listdict = new ListDictionary();

        // Adding elements to ListDictionary
        listdict.Add("1", "Ram");
        listdict.Add("2", "Shyam");
        listdict.Add("3", "Mohan");
        listdict.Add("4", "Sohan");
        listdict.Add("5", "Rohan");

        // Using the SyncRoot property
        lock(listdict.SyncRoot)
        {
            // foreach loop to display
            // the elements in listdict
            foreach(DictionaryEntry i in listdict)
                Console.WriteLine(i.Key + " ----> " + i.Value);
        }
    }
}
}
```

**Output:**

```cs
1 ----> Ram
2 ----> Shyam
3 ----> Mohan
4 ----> Sohan
5 ----> Rohan

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . list dictionary . sync root？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary.syncroot?view=netframework-4.7.2)