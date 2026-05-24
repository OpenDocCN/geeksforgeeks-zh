# C# |将堆栈复制到数组中

> 原文:[https://www . geeksforgeeks . org/c-sharp-将堆栈复制到阵列/](https://www.geeksforgeeks.org/c-sharp-copy-the-stack-to-an-array/)

**叠加< T >。复制到(T[]，Int32)方法**用于将堆栈< T >复制到从指定数组索引开始的现有一维数组中。

**属性:**

*   堆栈<t>的容量是堆栈<t>可以容纳的元素数量。当元素被添加到堆栈<t>中时，容量会根据需要通过重新分配自动增加。</t></t></t>
*   如果计数小于堆栈的容量<t>，推送是一个 0(1)操作。如果需要增加容量来容纳新元素，Push 将变成 O(n)操作，其中 n 是 Count。Pop 是一个 O(1)操作。</t>
*   堆栈接受 null 作为有效值，并允许重复元素。

**语法:**

```cs
public void CopyTo (T[] array, int arrayIndex);

```

**参数:**

> **数组:**一维数组，是从<**>栈复制的元素的目的地。数组必须具有从零开始的索引。**
> 
>  ****数组索引:**数组中开始复制的从零开始的索引。**

****异常:****

*   ****参数空异常:**如果一个*数组*为空。**
*   ****argumentout of range exception:**如果*数组索引*小于零。**
*   ****参数异常:**源堆栈< **T** >中的元素数量大于从*数组索引*到目标数组末尾的可用空间。**

**下面给出了一些例子，以便更好地理解实现:**

****例 1:****

```cs
// C# code to Copy the Stack to an Array
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

        // Creating a string array arr
        string[] arr = new string[myStack.Count];

        // Copying the elements of stack into array arr
        myStack.CopyTo(arr, 0);

        // Displaying the elements in array arr
        foreach(string str in arr)
        {
            Console.WriteLine(str);
        }
    }
}
```

****Output:**

```cs
GeeksforGeeks
Data Structures
Noida
Geeks Classes
Geeks

```** 

****例 2:****

```cs
// C# code to Copy the Stack to an Array
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

        // Creating an Integer array arr
        int[] arr = new int[myStack.Count];

        // Copying the elements of stack into array arr
        myStack.CopyTo(arr, 0);

        // Displaying the elements in array arr
        foreach(int i in arr)
        {
            Console.WriteLine(i);
        }
    }
}
```

****Output:**

```cs
6
5
4
3
2

```** 

****参考:****

*   **[https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . stack-1 . copy to？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.stack-1.copyto?view=netframework-4.7.2)**