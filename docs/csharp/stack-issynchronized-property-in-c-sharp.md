# 叠加。是 C# 中的同步属性

> 原文:[https://www . geesforgeks . org/stack-is synchronized-property-in-c-sharp/](https://www.geeksforgeeks.org/stack-issynchronized-property-in-c-sharp/)

该方法(属于*系统。Collections* 命名空间)用于获取一个值，该值指示对堆栈的访问是否同步(线程安全)。为了保证堆栈的线程安全，所有操作都必须通过 *Synchronized* 方法返回的包装器来完成。此外，检索该属性的值是一个*0(1)*操作。

**语法:**

```cs
public virtual bool IsSynchronized { get; }
```

**返回值:**如果对堆栈的访问是同步的(线程安全的)，该属性返回*真*，否则返回*假*。默认为*假*。

以下程序说明了上述属性的使用:

**例 1:**

```cs
// C# code to illustrate the
// Stack.IsSynchronized Property
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack
        Stack myStack = new Stack();

        // Inserting the elements into the Stack
        myStack.Push("Geeks");
        myStack.Push("Geeks Classes");
        myStack.Push("Noida");
        myStack.Push("Data Structures");
        myStack.Push("GeeksforGeeks");

        // Creates a synchronized
        // wrapper around the Stack
        Stack ss = Stack.Synchronized(myStack);

        // Displaying the synchronization
        // status of both Stack
        Console.WriteLine("myStack is {0}.", myStack.IsSynchronized ?
                                "Synchronized" : "Not Synchronized");

        Console.WriteLine("ss is {0}.", ss.IsSynchronized ? 
                      "Synchronized" : "Not Synchronized");
    }
}
```

**Output:**

```cs
myStack is Not Synchronized.
ss is Synchronized.

```

**例 2:**

```cs
// C# code to illustrate the
// Stack.IsSynchronized Property
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack
        Stack myStack = new Stack();

        // Inserting elements into Stack
        myStack.Push("1st");
        myStack.Push("2nd");
        myStack.Push("3rd");
        myStack.Push("4th");
        myStack.Push("5th");

        // the default is false for
        // IsSynchronized property
        Console.WriteLine(myStack.IsSynchronized);
    }
}
```

**Output:**

```cs
False

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . stack . is synchronized？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.stack.issynchronized?view=netframework-4.7.2)