# 叠加。C# 中的清除方法

> 原文:[https://www . geesforgeks . org/stack-clear-method-in-c-sharp/](https://www.geeksforgeeks.org/stack-clear-method-in-c-sharp/)

该方法(属于*系统。集合*命名空间)用于从堆栈中移除所有对象。此方法将堆栈计数设置为零，并且集合元素中对其他对象的引用也将被移除。这个方法是一个 O(n)运算，其中 n 是 Count。

**语法:**

```cs
public virtual void Clear ();
```

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to illustrate the
// Stack.Clear Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack
        Stack myStack = new Stack();

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
        Console.Write("Total number of elements"+
                         " in the Stack are : ");

        Console.WriteLine(myStack.Count);

        // Removing all elements from Stack
        myStack.Clear();

        // Displaying the count of elements
        // contained in the Stack after
        // removing all the elements
        Console.Write("Total number of elements"+
                         " in the Stack are : ");

        Console.WriteLine(myStack.Count);
    }
}
```

**输出:**

```cs
Total number of elements in the Stack are : 6
Total number of elements in the Stack are : 0

```