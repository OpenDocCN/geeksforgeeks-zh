# 叠加。C# 中的 Push()方法

> 原文:[https://www.geeksforgeeks.org/stack-push-method-in-c-sharp/](https://www.geeksforgeeks.org/stack-push-method-in-c-sharp/)

该方法(属于*系统。集合*命名空间)用于在堆栈顶部插入一个对象。如果计数已经等于容量，则通过自动重新分配内部数组来增加堆栈的容量，并在添加新元素之前将现有元素复制到新数组中。如果计数小于堆栈的容量，则推送是一个 0(1)操作。如果需要增加容量来容纳新元素，Push 将变成 O(n)操作，其中 n 是 Count。

**语法:**

```cs
public virtual void Push (object obj);

```

**示例:**

```cs
// C# code to demonstrate the 
// Stack.Push() Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack
        Stack myStack = new Stack();

        // Inserting the elements into the Stack
        myStack.Push("one");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements "+
                           "in the Stack are : ");

        Console.WriteLine(myStack.Count);

        myStack.Push("two");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements"+
                         " in the Stack are : ");

        Console.WriteLine(myStack.Count);

        myStack.Push("three");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements"+
                         " in the Stack are : ");

        Console.WriteLine(myStack.Count);

        myStack.Push("four");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements"+
                         " in the Stack are : ");

        Console.WriteLine(myStack.Count);

        myStack.Push("five");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements"+
                         " in the Stack are : ");

        Console.WriteLine(myStack.Count);

        myStack.Push("six");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements"+
                         " in the Stack are : ");

        Console.WriteLine(myStack.Count);
    }
}
```

**Output:**

```cs
Total number of elements in the Stack are : 1
Total number of elements in the Stack are : 2
Total number of elements in the Stack are : 3
Total number of elements in the Stack are : 4
Total number of elements in the Stack are : 5
Total number of elements in the Stack are : 6

```

**参考:**

*   [https://docs . Microsoft . com/ENA-us/dotnet/API/system . collections . stack . push？视图=netframework-4.7.2](https://docs.microsoft.com/ena-us/dotnet/api/system.collections.stack.push?view=netframework-4.7.2)