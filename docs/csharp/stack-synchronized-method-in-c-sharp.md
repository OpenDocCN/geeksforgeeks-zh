# 叠加。C# 中的 Synchronized()方法

> 原文:[https://www . geesforgeks . org/stack-synchronized-method in-c-sharp/](https://www.geeksforgeeks.org/stack-synchronized-method-in-c-sharp/)

该方法(属于*系统。集合*命名空间)用于返回堆栈的同步(线程安全)包装。为了保证堆栈的线程安全，所有操作都必须通过这个包装器来完成。

**语法:**

> 公共静态系统。集合。堆栈同步(系统。Collections . Stack

**返回值:**返回堆栈周围的同步包装。

**异常**:如果*栈*为空，这个方法会给出 *ArgumentNullException* 。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to illustrate the
// Stack.Synchronized() Method
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
        Stack st = Stack.Synchronized(myStack);

        // Displays the synchronization
        // status of both Stack
        Console.WriteLine("myStack is {0}.", myStack.IsSynchronized ?
                                "Synchronized" : "Not Synchronized");

        Console.WriteLine("st is {0}.", st.IsSynchronized ? 
                      "Synchronized" : "Not Synchronized");
    }
}
```

**输出:**

```cs
myStack is Not Synchronized.
st is Synchronized.

```

**例 2:**

```cs
// C# code to illustrate the
// Stack.Synchronized() Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack
        Stack myStack = new Stack();

        // Inserting the elements into the Stack
        myStack.Push("C");
        myStack.Push("C++");
        myStack.Push("Java");
        myStack.Push("C#");
        myStack.Push("Python");

        // it will give error as
        // the parameter is null
        Stack sq = Stack.Synchronized(null);
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentNullException:值不能为空。
> 参数名称:堆栈

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . stack . synchronized？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.stack.synchronized?view=netframework-4.7.2)