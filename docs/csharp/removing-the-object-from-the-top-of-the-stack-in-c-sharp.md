# 在 C# 中从堆栈顶部移除对象

> 原文:[https://www . geeksforgeeks . org/从 c-sharp 堆栈顶部移除对象/](https://www.geeksforgeeks.org/removing-the-object-from-the-top-of-the-stack-in-c-sharp/)

**叠加< T >。弹出方法**用于移除并返回堆栈顶部的对象< T >。这个方法属于*系统。集合.通用*命名空间。

**语法:**

```cs
public T Pop ();
```

**返回值:**返回要从堆栈顶部移除的对象。

**异常**:如果堆栈< T >为空，此方法将给出*无效操作异常*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# Program to illustrate the
// use of Stack<T>.Pop() Method
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    public static void Main()
    {

        // Creating a Stack of Strings
        Stack<string> myStack = new Stack<string>();

        // Inserting the elements into the Stack
        myStack.Push("Geeks");
        myStack.Push("Geeks Classes");
        myStack.Push("Noida");
        myStack.Push("Data Structures");
        myStack.Push("GeeksforGeeks");

        Console.WriteLine("Number of elements in the Stack: {0}",
                                                 myStack.Count);

        // Retrieveing top element of Stack
        Console.Write("Top element of Stack is: ");
        Console.Write(myStack.Pop());

        // printing the no of Stack element
        // after Pop operation
        Console.WriteLine("\nNumber of elements in the Stack: {0}",
                                                    myStack.Count);
    }
}
```

**Output:**

```cs
Number of elements in the Stack: 5
Top element of Stack is: GeeksforGeeks
Number of elements in the Stack: 4

```

**例 2:**

```cs
// C# Program to illustrate the
// use of Stack<T>.Pop() Method
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    public static void Main()
    {

        // Creating a Stack of integers
        Stack<int> myStack = new Stack<int>();

        // Inserting the elements into the Stack
        myStack.Push(7);
        myStack.Push(9);

        Console.WriteLine("Number of elements in the Stack: {0}",
                                                  myStack.Count);

        // Retrieveing top element of Stack
        Console.Write("Top element of Stack is: ");
        Console.Write(myStack.Pop());

        // printing the no of Stack element
        // after Pop operation
        Console.WriteLine("\nNumber of elements in the Stack: {0}",
                                                    myStack.Count);
    }
}
```

**Output:**

```cs
Number of elements in the Stack: 2
Top element of Stack is: 9
Number of elements in the Stack: 1

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . stack-1 . pop？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.stack-1.pop?view=netframework-4.7.2)