# C# |获取栈顶对象–Peek 操作

> 原文:[https://www . geeksforgeeks . org/c-sharp-获取堆栈顶部对象-peek-operation/](https://www.geeksforgeeks.org/c-sharp-get-object-at-the-top-of-the-stack-peek-operation/)

**[栈](https://www.geeksforgeeks.org/stack-data-structure/)** 代表一个 ***后进先出*** 的集合对象。当您需要后进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为**推动**项目，当您移除它时，它被称为**弹出**项目。**堆叠< T >。Peek 方法**用于返回堆栈顶部的对象< T >而不将其移除。此方法为 *O(1)* 操作。

**属性:**

*   堆栈的容量是堆栈可以容纳的元素数量。随着元素添加到堆栈中，容量会根据需要通过重新分配自动增加。
*   如果计数小于堆栈的容量，推送是一个*0(1)*操作。如果需要增加容量来容纳新元素，Push 将成为 *O(n)* 操作，其中 *n* 为 Count。Pop 是一个 *O(1)* 操作。
*   堆栈接受 null 作为有效值，并允许重复元素。

**语法:**

```cs
object Peek(); 

```

**返回值:**Peek()方法从类型为*系统的堆栈< T >中返回最后一个(最上面的)值。对象*。

**异常:**在空栈上调用 Peek()方法会抛出***invalid operationexception***。所以在使用 Peek()方法检索元素之前，一定要检查堆栈中的元素。

下面给出了一些例子，以便更好地理解实现。

**例 1:**

```cs
// C# code to Get object at
// the top of the Stack
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack of strings
        Stack<string> myStack = new Stack<string>();

        // Inserting the elements into the Stack
        myStack.Push("1st Element");
        myStack.Push("2nd Element");
        myStack.Push("3rd Element");
        myStack.Push("4th Element");
        myStack.Push("5th Element");
        myStack.Push("6th Element");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements in the Stack are : ");

        Console.WriteLine(myStack.Count);

        // Displaying the top element of Stack
        // without removing it from the Stack
        Console.WriteLine("Element at the top is : " + myStack.Peek());

        // Displaying the top element of Stack
        // without removing it from the Stack
        Console.WriteLine("Element at the top is : " + myStack.Peek());

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements in the Stack are : ");

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
// C# code to Get object at
// the top of the Stack
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack of Integers
        Stack<int> myStack = new Stack<int>();

        // Displaying the top element of Stack
        // without removing it from the Stack
        // Calling Peek() method on empty stack
        // will throw InvalidOperationException.
        Console.WriteLine("Element at the top is : " + myStack.Peek());
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。无效操作异常:堆栈为空。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . stack . peek？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.stack.peek?view=netframework-4.7.2)