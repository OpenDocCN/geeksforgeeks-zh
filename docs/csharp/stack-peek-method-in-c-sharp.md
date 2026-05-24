# 叠加。C# 中的 Peek 方法

> 原文:[https://www.geeksforgeeks.org/stack-peek-method-in-c-sharp/](https://www.geeksforgeeks.org/stack-peek-method-in-c-sharp/)

该方法(属于*系统。集合*命名空间)用于返回堆栈顶部的对象，而不移除它。此方法类似于 Pop 方法，但 Peek 不会修改 Stack。

**语法:**

```cs
public virtual object Peek ();

```

**返回值:**返回栈顶的对象。

**异常:**在空栈上调用 Peek()方法会抛出***invalid operationexception***。所以在使用 Peek()方法检索元素之前，一定要检查堆栈中的元素。

下面给出了一些例子，以便更好地理解实现。

**例 1:**

```cs
// C# code to illustrate the
// Stack.Peek Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack
        Stack myStack = new Stack();

        // Inserting the elements into the Stack
        myStack.Push("1st Element");
        myStack.Push("2nd Element");
        myStack.Push("3rd Element");
        myStack.Push("4th Element");
        myStack.Push("5th Element");
        myStack.Push("6th Element");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements"+
                         " in the Stack are : ");

        Console.WriteLine(myStack.Count);

        // Displaying the top element of Stack
        // without removing it from the Stack
        Console.WriteLine("Element at the top is : " 
                                  + myStack.Peek());

        // Displaying the top element of Stack
        // without removing it from the Stack
        Console.WriteLine("Element at the top is : " 
                                + myStack.Peek());

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements "+
                           "in the Stack are : ");

        Console.WriteLine(myStack.Count);
    }
}
```

**输出:**

```cs
Total number of elements in the Stack are : 6
Element at the top is : 6th Element
Element at the top is : 6th Element
Total number of elements in the Stack are : 6

```

**例 2:**

```cs
// C# code to illustrate the
// Stack.Peek Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack
        Stack myStack = new Stack();

        // Displaying the top element of Stack
        // without removing it from the Stack
        // Calling Peek() method on empty stack
        // will throw InvalidOperationException.
        Console.WriteLine("Element at the top is : " 
                               + myStack.Peek());
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。无效操作异常:堆栈为空。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . stack . peek？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.stack.peek?view=netframework-4.7.2)