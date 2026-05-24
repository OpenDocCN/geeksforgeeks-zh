# 叠加。C# 中的 ToArray()方法

> 原文:[https://www . geesforgeks . org/stack-to array-method-in-c-sharp/](https://www.geeksforgeeks.org/stack-toarray-method-in-c-sharp/)

该方法(属于*系统。集合*命名空间)用于将*堆栈*复制到新数组。元素以后进先出(LIFO)的顺序复制到数组中，类似于对 Pop 的连续调用所返回的元素的顺序。这个方法是一个 O(n)运算，其中 n 是 Count。

**语法:**

```cs
public virtual object[] ToArray ();

```

**返回类型:**该方法返回类型为*系统的新数组。对象*包含堆栈元素的副本。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to illustrate the
// Stack.ToArray() Method
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

        // Converting the Stack into array
        Object[] arr = myStack.ToArray();

        // Displaying the elements in array
        foreach(Object str in arr)
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
// Stack.ToArray() Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack
        Stack myStack = new Stack();

        // Inserting the elements into the Stack
        myStack.Push(2);
        myStack.Push(3);
        myStack.Push(4);
        myStack.Push(5);
        myStack.Push(6);

        // Converting the Stack into array
        Object[] arr = myStack.ToArray();

        // Displaying the elements in array
        foreach(Object i in arr)
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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . stack . to array？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.stack.toarray?view=netframework-4.7.2)