# 获取在 C# 中遍历堆栈的枚举器

> 原文:[https://www . geeksforgeeks . org/get-一个在 c-sharp 中迭代堆栈的枚举器/](https://www.geeksforgeeks.org/getting-an-enumerator-that-iterates-through-the-stack-in-c-sharp/)

**堆叠< T >。GetEnumerator 方法**用于获取迭代堆栈的 [IEnumerator](https://docs.microsoft.com/en-us/dotnet/api/system.collections.ienumerator?view=netframework-4.7.2) 。它属于`System.Collections.Generic`命名空间。

**语法:**

```cs
public System.Collections.Generic.Stack<T>.Enumerator GetEnumerator ();
```

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// Stack<T>.GetEnumerator Method
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

        // To get an Enumerator
        // for the Stack
        IEnumerator<string> enumerator = 
         myStack.GetEnumerator();

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