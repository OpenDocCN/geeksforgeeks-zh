# 如何在 C# 中同步访问堆栈

> 原文:[https://www . geesforgeks . org/如何同步访问 c-sharp 中的堆栈/](https://www.geeksforgeeks.org/how-to-get-synchronize-access-to-the-stack-in-c-sharp/)

**堆叠。同步根属性**用于获取一个对象，该对象可用于同步对[堆栈](https://www.geeksforgeeks.org/c-sharp-stack-class/)的访问。Stack 表示对象的后进先出集合。当您需要后进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为推送项目，当您删除它时，它被称为弹出项目。这个类属于`System.Collections` 命名空间。

> **语法:**公共虚拟对象 SyncRoot { get}
> 
> **属性值:**可用于同步访问堆栈的对象。

**要点:**

*   完成对象同步后，只有一个线程可以操作堆栈中的数据。
*   属性是提供读取、写入和计算私有数据字段的方法的类的成员。
*   同步代码不能直接在集合上执行，因此它必须在集合的同步根上执行操作，以保证从其他对象派生的集合的正确操作。
*   检索该属性的值是一个 O(1)操作。

以下程序说明了上述属性的使用:

**示例 1:** 在这段代码中，我们使用 SyncRoot 来获得对名为 *st* 的堆栈的同步访问，这不是一个线程安全的过程，可能会导致异常。所以为了避免异常，我们在枚举期间锁定集合。

```cs
// C# program to illustrate the
// use of SyncRoot property of
// the Stack
using System;
using System.Threading;
using System.Collections;

namespace sync_root {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Declaring an Stack
        Stack st = new Stack();

        // Adding elements to Stack
        st.Push(1);
        st.Push(2);
        st.Push(3);
        st.Push(4);
        st.Push(5);

        // Using the SyncRoot property
        lock(st.SyncRoot)
        {
            // foreach loop to display
            // the elements in st
            foreach(Object i in st)
                Console.WriteLine(i);
        }
    }
}
}
```

**Output:**

```cs
5
4
3
2
1

```

**例 2:**

```cs
// C# program to illustrate the
// use of SyncRoot property of
// the Stack
using System;
using System.Threading;
using System.Collections;

namespace sync_root {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Declaring an Stack
        Stack st = new Stack();

        // Adding elements to Stack
        st.Push("C");
        st.Push("C++");
        st.Push("Java");
        st.Push("C#");
        st.Push("HTML");

        // Using the SyncRoot property
        lock(st.SyncRoot)
        {
            // foreach loop to display
            // the elements in st
            foreach(Object i in st)
                Console.WriteLine(i);
        }
    }
}
}
```

**Output:**

```cs
HTML
C#
Java
C++
C

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . stack . sync root？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.stack.syncroot?view=netframework-4.7.2)