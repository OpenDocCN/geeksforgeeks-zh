# C# |从堆栈中移除所有对象

> 原文:[https://www . geesforgeks . org/c-从堆栈中移除所有对象/](https://www.geeksforgeeks.org/c-remove-all-objects-from-the-stack/)

**[栈](https://www.geeksforgeeks.org/stack-data-structure/)** 代表一个 ***后进先出*** 的集合对象。当您需要后进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为**推动**项目，当您移除它时，它被称为**弹出**项目。**堆叠< T >。清除方法**用于从堆栈中移除所有对象< T >。此方法为 *O(n)* 操作，其中 *n* 为计数。

**属性:**

*   堆栈的容量是堆栈可以容纳的元素数量。随着元素添加到堆栈中，容量会根据需要通过重新分配自动增加。
*   如果计数小于堆栈的容量，推送是一个*0(1)*操作。如果需要增加容量来容纳新元素，Push 将成为 *O(n)* 操作，其中 *n* 为 Count。Pop 是一个 *O(1)* 操作。
*   堆栈接受 null 作为有效值，并允许重复元素。

**语法:**

```cs
public virtual void Clear();

```

下面给出了一些例子，以便更好地理解实现。

**例 1:**

```cs
// C# code to Remove all
// objects from the Stack
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
        // contained in the Stack before
        // removing all the elements
        Console.Write("Total number of elements in the Stack are : ");

        Console.WriteLine(myStack.Count);

        // Removing all elements from Stack
        myStack.Clear();

        // Displaying the count of elements
        // contained in the Stack after
        // removing all the elements
        Console.Write("Total number of elements in the Stack are : ");

        Console.WriteLine(myStack.Count);
    }
}
```

**Output:**

```cs
Total number of elements in the Stack are : 6
Total number of elements in the Stack are : 0

```

**例 2:**

```cs
// C# code to Remove all
// objects from the Stack
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack of Integers
        Stack<int> myStack = new Stack<int>();

        // Inserting the elements into the Stack
        myStack.Push(3);
        myStack.Push(5);
        myStack.Push(7);
        myStack.Push(9);
        myStack.Push(11);

        // Displaying the count of elements
        // contained in the Stack before
        // removing all the elements
        Console.Write("Total number of elements in the Stack are : ");

        Console.WriteLine(myStack.Count);

        // Removing all elements from Stack
        myStack.Clear();

        // Displaying the count of elements
        // contained in the Stack after
        // removing all the elements
        Console.Write("Total number of elements in the Stack are : ");

        Console.WriteLine(myStack.Count);
    }
}
```

**Output:**

```cs
Total number of elements in the Stack are : 5
Total number of elements in the Stack are : 0

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . stack . clear？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.stack.clear?view=netframework-4.7.2)