# C# |如何创建堆栈

> 原文:[https://www . geeksforgeeks . org/c-sharp-如何创建堆栈/](https://www.geeksforgeeks.org/c-sharp-how-to-create-a-stack/)

**Stack()构造函数**用于初始化 Stack 类的一个新实例，该实例将为空，并具有默认的初始容量。[堆栈](https://www.geeksforgeeks.org/c-sharp-stack-class/)代表后进先出的对象集合。当您需要后进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为推送项目，当您删除它时，它被称为弹出项目。这个类属于`System.Collections` 命名空间。

**语法:**

```cs
public Stack ();
```

**要点:**

*   The number of elements that can be accommodated in a stack is called stack capacity. If the element is to be added to the stack, the capacity will be automatically increased by reallocating the internal array.
*   If the size of the collection can be estimated, specifying the initial capacity will eliminate the need to perform a large number of resizing operations when adding elements to the stack.
*   This constructor is an O(1) operation.

**例 1:**

```cs
// C# Program to illustrate how
// to create a Stack
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // st is the Stack object
        // Stack() is the constructor
        // used to initializes a new
        // instance of the Stack class
        Stack st = new Stack();

        // Count property is used to get the
        // number of elements in Stack
        // It will give 0 as no elements
        // are present currently
        Console.WriteLine(st.Count);
    }
}
```

**输出:**

```cs
0

```