# 叠加。C# 中的 GetEnumerator 方法

> 原文:[https://www . geesforgeks . org/stack-getenumerator-method-in-c-sharp/](https://www.geeksforgeeks.org/stack-getenumerator-method-in-c-sharp/)

这个方法返回一个迭代堆栈的[迭代函数](https://docs.microsoft.com/en-us/dotnet/api/system.collections.ienumerator?view=netframework-4.7.2)。它属于`System.Collections`命名空间。

**语法:**

```cs
public virtual System.Collections.IEnumerator GetEnumerator ();
```

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// Stack.GetEnumerator Method
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

        // To get an Enumerator
        // for the Stack
        IEnumerator enumerator = myStack.GetEnumerator();

        // If MoveNext passes the end of the
        // collection, the enumerator is positioned
        // after the last element in the Stack
        // and MoveNext returns false.
        while (enumerator.MoveNext()) {

            Console.WriteLine(enumerator.Current);
        }
    }
}
```

**输出:**

```cs
GeeksforGeeks
Data Structures
Noida
Geeks Classes
Geeks

```