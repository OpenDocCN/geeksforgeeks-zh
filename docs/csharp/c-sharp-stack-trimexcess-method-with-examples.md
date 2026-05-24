# C# |栈<t>。带示例的三进制方法</t>T3

> 原文:[https://www . geeksforgeeks . org/c-sharp-stack-trimexcess-method-with-examples/](https://www.geeksforgeeks.org/c-sharp-stack-trimexcess-method-with-examples/)

**[堆叠](https://www.geeksforgeeks.org/stack-data-structure/)** 代表后进先出的集合对象。当您需要后进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为推送项目，当您删除它时，它被称为弹出项目。
**叠加< T >。TrimExcess 方法**用于将容量设置为队列中元素的实际数量< **T** >，如果该数量小于当前容量的 90%。

堆栈是一种无界的数据结构，在 C# 中没有计算堆栈容量的方法。它是动态的，取决于系统内存。这种方法通常用于大型堆栈的内存管理。

**堆叠属性:**

*   堆栈的容量是堆栈可以容纳的元素数量。随着元素添加到堆栈中，容量会根据需要通过重新分配自动增加。
*   如果计数小于堆栈的容量，则推送是一个 0(1)操作。如果需要增加容量来容纳新元素，Push 将变成 O(n)操作，其中 n 是 Count。Pop 是一个 O(1)操作。
*   堆栈接受 null 作为有效值，并允许重复元素。

**语法:**

```cs
public void TrimExcess ();

```

**注:**

*   如果没有新元素添加到集合中，此方法可用于最小化集合的内存开销。
*   要将堆栈< **T** >重置为其初始状态，请在调用 TrimExcess 方法之前调用 [Clear](https://www.geeksforgeeks.org/c-remove-all-objects-from-the-stack/) 方法。
*   修剪空堆栈< **T** >将堆栈< **T** >的容量设置为默认容量。

**示例:**

```cs
// C# code to set the capacity to the
// actual number of elements in the Stack
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack of strings
        Stack<string> myStack = new Stack<string>();

        // Inserting elements into Stack
        myStack.Push("1st");
        myStack.Push("2nd");
        myStack.Push("3rd");
        myStack.Push("4th");
        myStack.Push("5th");

        // To display number of elements in Stack
        Console.WriteLine(myStack.Count);

        // removing all the elements from the stack
        myStack.Clear();

        // using TrimExcess method
        myStack.TrimExcess();

        // To display number of elements in Stack
        Console.WriteLine(myStack.Count);
    }
}
```

**Output:**

```cs
5
0

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . stack-1 . tri excess？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.stack-1.trimexcess?view=netframework-4.7.2)