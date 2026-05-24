# C# |将堆栈转换为数组

> 原文:[https://www . geesforgeks . org/c-sharp-convert-stack-to-array/](https://www.geeksforgeeks.org/c-sharp-convert-stack-to-array/)

**[栈](https://www.geeksforgeeks.org/stack-data-structure/)** 代表一个 ***后进先出*** 的集合对象。当您需要后进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为**推动**项目，当您移除它时，它被称为**弹出**项目。**堆叠< T >。ToArray 方法**用于将一个*栈<T>T15】复制到一个新的数组中。*

**属性:**

*   堆栈的容量是堆栈可以容纳的元素数量。随着元素添加到堆栈中，容量会根据需要通过重新分配自动增加。
*   如果计数小于堆栈的容量，则推送是一个 0(1)操作。如果需要增加容量来容纳新元素，Push 将变成 O(n)操作，其中 n 是 Count。Pop 是一个 O(1)操作。
*   堆栈接受 null 作为有效值，并允许重复元素。

**语法:**

```cs
public T[] ToArray ();

```

**返回类型:**该方法返回一个*新数组 t[]* ，其中包含*栈< T >* 元素的副本。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to Convert Stack to array
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

        // Converting the Stack into array
        String[] arr = myStack.ToArray();

        // Displaying the elements in array
        foreach(string str in arr)
        {
            Console.WriteLine(str);
        }
    }
}
```

**Output:**

```cs
GeeksforGeeks
Data Structures
Noida
Geeks Classes
Geeks

```

**例 2:**

```cs
// C# code to Convert Stack to array
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack of Integers
        Stack<int> myStack = new Stack<int>();

        // Inserting the elements into the Stack
        myStack.Push(2);
        myStack.Push(3);
        myStack.Push(4);
        myStack.Push(5);
        myStack.Push(6);

        // Converting the Stack into array
        int[] arr = myStack.ToArray();

        // Displaying the elements in array
        foreach(int i in arr)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
6
5
4
3
2

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . stack-1 . to array？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.stack-1.toarray?view=netframework-4.7.2)