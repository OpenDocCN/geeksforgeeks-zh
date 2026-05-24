# C# |从集合中创建堆栈

> 原文:[https://www . geeksforgeeks . org/c-sharp-从集合中创建堆栈/](https://www.geeksforgeeks.org/c-sharp-create-a-stack-from-a-collection/)

[栈](https://www.geeksforgeeks.org/stack-data-structure/)代表一个 ***后进先出*** 的集合对象。当您需要后进先出访问项目时，可以使用它。当你在列表中添加一个项目时，它被称为**推动**项目，当你移除它时，它被称为**弹出**项目。创建堆栈意味着向堆栈中添加项目。**堆叠< T >。推(对象)方法**用于在堆栈顶部插入一个对象。

**属性:**

*   堆栈的容量是堆栈可以容纳的元素数量。随着元素添加到堆栈中，容量会根据需要通过重新分配自动增加。
*   如果计数小于堆栈的容量，推送是一个*0(1)*操作。如果需要增加容量来容纳新元素，Push 将成为 *O(n)* 操作，其中 *n* 为 Count。Pop 是一个 *O(1)* 操作。
*   堆栈接受 null 作为有效值，并允许重复元素。

**语法:**

```cs
public virtual void Push (object obj);
```

**参数:**

> **物体类型*系统。对象*是推上堆栈< T >。该值可以是*空值*。**

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to Create a Stack
// from a collection
using System;
using System.Collections.Generic;

class GFG {
    // Driver code
    public static void Main()
    {
        // Creating a Stack of strings
        Stack<string> myStack1 = new Stack<string>();

        // Inserting the elements into the Stack
        myStack1.Push("GeeksforGeeks");
        myStack1.Push("is");
        myStack1.Push("the");
        myStack1.Push("best");
        myStack1.Push("website");

        // Displaying the count of elements
        // contained in the myStack1
        Console.Write("Total number of elements in the Stack 1 are : ");

        Console.WriteLine(myStack1.Count);

        // Displaying the elements in Stack myStack1
        foreach(string str in myStack1)
        {
            Console.WriteLine(str);
        }

        // Creating a Stack from a collection
        Stack<string> myStack2 = new Stack<string>(myStack1.ToArray());

        // Displaying the count of elements
        // contained in the myStack2
        Console.Write("Total number of elements in the Stack 2 are : ");

        Console.WriteLine(myStack2.Count);

        // Displaying the elements in Stack myStack2
        foreach(string str in myStack2)
        {
            Console.WriteLine(str);
        }
    }
}
```

**Output:**

```cs
Total number of elements in the Stack 1 are : 5
website
best
the
is
GeeksforGeeks
Total number of elements in the Stack 2 are : 5
GeeksforGeeks
is
the
best
website

```

**例 2:**

```cs
// C# code to Create a Stack
// from a collection
using System;
using System.Collections.Generic;

class GFG {
    // Driver code
    public static void Main()
    {
        // Creating a Stack of Integers
        Stack<int> myStack1 = new Stack<int>();

        // Inserting the elements into the Stack
        myStack1.Push(5);
        myStack1.Push(10);
        myStack1.Push(15);
        myStack1.Push(20);
        myStack1.Push(25);

        // Displaying the count of elements
        // contained in the myStack1
        Console.Write("Total number of elements in the Stack 1 are : ");

        Console.WriteLine(myStack1.Count);

        // Displaying the elements in Stack myStack1
        foreach(int i in myStack1)
        {
            Console.WriteLine(i);
        }

        // Creating a Stack from a collection
        Stack<int> myStack2 = new Stack<int>(myStack1.ToArray());

        // Displaying the count of elements
        // contained in the myStack2
        Console.Write("Total number of elements in the Stack 2 are : ");

        Console.WriteLine(myStack2.Count);

        // Displaying the elements in Stack myStack2
        foreach(int i in myStack2)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
Total number of elements in the Stack 1 are : 5
25
20
15
10
5
Total number of elements in the Stack 2 are : 5
5
10
15
20
25

```

**参考:**[https://docs . Microsoft . com/en-us/dotnet/API/system . collections . stack . push？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.stack.push?view=netframework-4.7.2)