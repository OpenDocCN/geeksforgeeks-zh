# 叠加。在 C# 中包含()方法

> 原文:[https://www . geesforgeks . org/stack-contains-method-in-c-sharp/](https://www.geeksforgeeks.org/stack-contains-method-in-c-sharp/)

该方法(属于*系统。集合*命名空间)用于检查指定元素是否存在是否为堆栈。在内部，这个方法通过调用*对象来检查是否相等。等于*法。此外，它执行[线性搜索](https://www.geeksforgeeks.org/linear-search/)，因此，该方法是 *O(n)* 操作，其中 n 是计数。

**语法:**

```cs
public virtual bool Contains (object obj);
```

这里， *obj* 是要在堆栈中定位的对象。该值可以是*空值*。

**返回值:**如果在堆栈中找到*对象*，返回*真*，否则返回*假*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to illustrate the
// Stack.Contains() Method
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

        // Checking whether the element is
        // present in the Stack or not
        // The function returns True if the
        // element is present in the Stack, 
        // else returns False
        Console.WriteLine(myStack.Contains("GeeksforGeeks"));
    }
}
```

**Output:**

```cs
True

```

**例 2:**

```cs
// C# code to illustrate the
// Stack.Contains() Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack
        Stack myStack = new Stack();

        // Inserting the elements 
        // into the Stack
        myStack.Push(5);
        myStack.Push(10);
        myStack.Push(15);
        myStack.Push(20);
        myStack.Push(25);

        // Checking whether the element is
        // present in the Stack or not
        // The function returns True if the
        // element is present in the Stack, else
        // returns False
        Console.WriteLine(myStack.Contains(7));
    }
}
```

**Output:**

```cs
False

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . stack . contains？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.stack.contains?view=netframework-4.7.2)