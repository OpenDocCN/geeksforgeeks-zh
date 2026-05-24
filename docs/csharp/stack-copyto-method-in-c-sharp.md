# 叠加。C# 中的 CopyTo()方法

> 原文:[https://www . geesforgeks . org/stack-copy to-method-in-c-sharp/](https://www.geeksforgeeks.org/stack-copyto-method-in-c-sharp/)

该方法(属于*系统。集合*命名空间)用于将堆栈复制到现有的[一维数组](https://www.geeksforgeeks.org/c-sharp-arrays/)，该数组从指定的数组索引开始。元素以后进先出(LIFO)的顺序复制到数组中，类似于对 Pop 的连续调用所返回的元素的顺序。这个方法是一个 O(n)运算，其中 n 是 Count。

**语法:**

```cs
public void CopyTo (T[] array, int arrayIndex);

```

**参数:**

> **数组:**是一维数组，是从 Stack 复制的元素的目的地。数组必须具有从零开始的索引。
> 
> **数组索引:**是*数组*中开始复制的从零开始的索引。

**异常:**

*   **参数空异常:**如果一个*数组*为空。
*   **argumentoutofrangerexception:**如果*指数*小于零。
*   **ArgumentException :** 如果数组是多维的或者源 Stack 中的元素数量大于从索引到目标数组末尾的可用空间。
*   **InvalidCastException** :如果源堆栈的类型不能自动转换为目的地*数组的类型*。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to illustrate the
// Stack.CopyTo() Method
using System;
using System.Collections;

class GFG {

    // Driver code
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

        // Creating a string array arr
        string[] arr = new string[myStack.Count];

        // Copying the elements of
        // stack into array arr
        myStack.CopyTo(arr, 0);

        // Displaying the elements
        // in array arr
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
// C# code to illustrate the
// Stack.CopyTo() Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack
        Stack myStack = new Stack();

        // Inserting the elements
        // into the Stack
        myStack.Push(2);
        myStack.Push(3);
        myStack.Push(4);
        myStack.Push(5);
        myStack.Push(6);

        // Creating an Integer array arr
        int[] arr = new int[myStack.Count];

        // Copying the elements of 
        // stack into array arr
        myStack.CopyTo(arr, 0);

        // Displaying the elements
        // in array arr
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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . stack . copy to？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.stack.copyto?view=netframework-4.7.2)