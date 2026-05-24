# C# |在栈顶插入一个对象–推送操作

> 原文:[https://www . geesforgeks . org/c-sharp-在堆栈顶部插入对象-推送操作/](https://www.geeksforgeeks.org/c-sharp-insert-an-object-at-the-top-of-the-stack-push-operation/)

**[栈](https://www.geeksforgeeks.org/stack-data-structure/)** 代表一个 ***后进先出*** 的集合对象。当您需要后进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为**推动**项目，当您移除它时，它被称为**弹出**项目。**堆叠< T >。推(T)** 方法用于在堆栈顶部插入一个对象< T >。

**属性:**

*   堆栈<t>的容量是堆栈<t>可以容纳的元素数量。当元素被添加到堆栈<t>中时，容量会根据需要通过重新分配自动增加。</t></t></t>
*   如果计数小于堆栈的容量，则推送是一个 0(1)操作。如果需要增加容量来容纳新元素，Push 将变成 O(n)操作，其中 n 是 Count。Pop 是一个 O(1)操作。
*   堆栈<t>接受 null 作为有效值，并允许重复元素。</t>

**语法:**

```cs
void Push(object obj);

```

**示例:**

```cs
// C# code to insert an object
// at the top of the Stack
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack of strings
        Stack<string> myStack = new Stack<string>();

        // Inserting the elements into the Stack
        myStack.Push("one");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements in the Stack are : ");

        Console.WriteLine(myStack.Count);

        myStack.Push("two");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements in the Stack are : ");

        Console.WriteLine(myStack.Count);

        myStack.Push("three");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements in the Stack are : ");

        Console.WriteLine(myStack.Count);

        myStack.Push("four");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements in the Stack are : ");

        Console.WriteLine(myStack.Count);

        myStack.Push("five");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements in the Stack are : ");

        Console.WriteLine(myStack.Count);

        myStack.Push("six");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements in the Stack are : ");

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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . stack-1 . push？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.stack-1.push?view=netframework-4.7.2)