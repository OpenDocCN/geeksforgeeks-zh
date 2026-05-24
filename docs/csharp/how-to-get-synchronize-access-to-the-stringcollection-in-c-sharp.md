# 如何在 C# 中同步访问 string collection

> 原文:[https://www . geeksforgeeks . org/如何同步访问 c-sharp 中的字符串集合/](https://www.geeksforgeeks.org/how-to-get-synchronize-access-to-the-stringcollection-in-c-sharp/)

**StringCollection。同步根属性**用于获取一个对象，该对象可用于同步对[字符串集合](https://www.geeksforgeeks.org/c-sharp-stringcollection-class/)的访问。表示字符串集合的类库。在*系统中定义了字符串集合类。集合。专用*命名空间。

> **语法:**公共虚拟对象 SyncRoot { get}
> 
> **属性值:**可用于同步访问字符串集合的对象。

**要点:**

*   完成对象的同步后，只有一个线程可以操作 StringCollection 中的数据。
*   属性是提供读取、写入和计算私有数据字段的方法的类的成员。
*   同步代码不能直接在集合上执行，因此它必须在集合的同步根上执行操作，以保证从其他对象派生的集合的正确操作。
*   检索该属性的值是一个 O(1)操作。

以下程序说明了上述属性的使用:

**示例 1:** 在这段代码中，我们使用 SyncRoot 来获得名为 *st* 的 StringCollection 的 Synchronized 访问，这不是一个线程安全的过程，可能会导致异常。所以为了避免异常，我们在枚举期间锁定集合。

```cs
// C# program to illustrate the
// use of SyncRoot property of
// the StringCollection class
using System;
using System.Threading;
using System.Collections;
using System.Collections.Specialized;

namespace sync_root {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Declaring an StringCollection
        StringCollection st = new StringCollection();

        // Adding elements to StringCollection
        st.Add("C");
        st.Add("C++");
        st.Add("Java");
        st.Add("C#");
        st.Add("HTML");

        // Using the SyncRoot property
        lock(st.SyncRoot)
        {
            foreach(object ob in st)
            {
                Console.WriteLine(ob);
            }
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

**例 2:**

```cs
// C# program to illustrate the
// use of SyncRoot property of
// the StringCollection class
using System;
using System.Threading;
using System.Collections;
using System.Collections.Specialized;

namespace sync_root {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Declaring an StringCollection
        StringCollection st = new StringCollection();

        // Adding elements to StringCollection
        st.Add("Geeks");
        st.Add("Classes");
        st.Add("on");
        st.Add("Data Structure");
        st.Add("Noida");

        // Using the SyncRoot property
        lock(st.SyncRoot)
        {
            foreach(object ob in st)
            {
                Console.WriteLine(ob);
            }
        }
    }
}
}
```

**Output:**

```cs
Geeks
Classes
on
Data Structure
Noida

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string collection . sync root？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.syncroot?view=netframework-4.7.2)