# 叠加。C# 中的克隆()方法

> 原文:[https://www . geesforgeks . org/stack-clone-method-in-c-sharp/](https://www.geeksforgeeks.org/stack-clone-method-in-c-sharp/)

此方法用于创建堆栈的 *[浅拷贝](https://www.geeksforgeeks.org/shallow-copy-and-deep-copy-in-c-sharp/)* 。它只是创建一个堆栈的副本。副本将引用内部数据阵列的克隆，但不引用原始内部数据阵列。

> **语法:**公共虚拟对象 Clone()；
> 
> **返回值:**该方法返回的对象只是堆栈的浅拷贝。

**示例 1:** 让我们看一个不使用 Clone()方法，而是使用赋值运算符“=”直接复制堆栈的示例。在下面的代码中，我们可以看到，即使我们从 *myStack2* 中弹出()元素，myStack 的内容也会发生变化。这是因为“=”只是将 myStack 的引用分配给 myStack2，并没有创建任何新的 Stack。但是 Clone()会创建一个新的堆栈。

```cs
// C# program to Copy a Stack using 
// the assignment operator
using System;
using System.Collections;

class GFG {

    // Main Method
    public static void Main(string[] args)
    {

        Stack myStack = new Stack();
        myStack.Push("C");
        myStack.Push("C++");
        myStack.Push("Java");
        myStack.Push("C#");

        // Creating a copy using the
        // assignment operator.
        Stack myStack2 = myStack; 

        // Removing top most element
        myStack2.Pop(); 
        PrintValues(myStack);
    }

    public static void PrintValues(IEnumerable myCollection)
    {
        // This method prints all
        // the elements in the Stack.
        foreach(Object obj in myCollection)
            Console.WriteLine(obj);
    }
}
```

**输出:**

```cs
Java
C++
C

```