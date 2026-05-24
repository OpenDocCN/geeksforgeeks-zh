# 叠加。C# 中的 Pop()方法

> 原文:[https://www.geeksforgeeks.org/stack-pop-method-in-c-sharp/](https://www.geeksforgeeks.org/stack-pop-method-in-c-sharp/)

该方法(属于*系统。集合*命名空间)用于移除并返回堆栈顶部的对象。此方法类似于 Peek 方法，但 Peek 不会修改堆栈。

**语法:**

```cs
public virtual object Pop ();
```

**返回值:**返回从栈顶移除的对象。

**异常**:如果堆栈为空，该方法将给出*无效操作异常*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# Program to illustrate the 
// use of Stack.Pop() Method
using System;
using System.Collections;

class GFG {

    // Main Method
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
// use of Stack.Pop() Method
using System;
using System.Collections;

class GFG {

    // Main Method
    public static void Main()
    {

        // Creating a Stack
        Stack myStack = new Stack();

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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . stack . pop？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.stack.pop?view=netframework-4.7.2)