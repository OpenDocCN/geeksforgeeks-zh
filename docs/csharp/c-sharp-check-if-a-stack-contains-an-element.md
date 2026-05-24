# C# |检查堆栈是否包含元素

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-a-stack-contain-a-element/](https://www.geeksforgeeks.org/c-sharp-check-if-a-stack-contains-an-element/)

**[栈](https://www.geeksforgeeks.org/stack-data-structure/)** 代表一个 ***后进先出*** 的集合对象。
**堆叠< T >。Contains(Object)方法**用于检查堆栈中是否有元素< T >。

**语法:**

```cs
public virtual bool Contains(object obj);

```

**返回值:**如果元素存在于堆栈中，函数返回*真*<T>如果元素不存在于堆栈中，函数返回*假*。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to Check if a Stack
// contains an element
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack of strings
        Stack<string> myStack = new Stack<string>();

        // Inserting the elements into the Stack
        myStack.Push("Geeks");
        myStack.Push("Geeks Classes");
        myStack.Push("Noida");
        myStack.Push("Data Structures");
        myStack.Push("GeeksforGeeks");

        // Checking whether the element is
        // present in the Stack or not
        // The function returns True if the
        // element is present in the Stack, else
        // returns False
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
// C# code to Check if a Stack
// contains an element
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack of Integers
        Stack<int> myStack = new Stack<int>();

        // Inserting the elements into the Stack
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