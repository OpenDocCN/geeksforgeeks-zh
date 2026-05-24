# C# | 在栈顶插入一个对象–推送操作

> 原文: [https://www.geeksforgeeks.org/c-sharp-insert-an-object-at-the-top-of-the-stack-push-operation/](https://www.geeksforgeeks.org/c-sharp-insert-an-object-at-the-top-of-the-stack-push-operation/)

[栈](https://www.geeksforgeeks.org/stack-data-structure/) 代表一个后进先出的集合对象。当您需要后进先出访问项目时，可以使用它。当您在列表中添加一个项目时，它被称为推动项目，当您移除它时，它被称为弹出项目。`Stack<T>.Push(T)` 方法用于在栈顶部插入一个对象`<T>`。

## 属性

*   `Stack<T>`的容量是`Stack<T>`可以容纳的元素数量。当元素被添加到`Stack<T>`中时，容量会根据需要通过重新分配自动增加。
*   如果`Count`小于栈的容量，则`Push`是一个 O(1)操作。如果需要增加容量来容纳新元素，`Push`将变成 O(n)操作，其中 n 是`Count`。`Pop`是一个 O(1)操作。
*   `Stack<T>`接受`null`作为有效值，并允许重复元素。

## 语法

```cs
void Push(object obj);
```

## 示例

```cs
// C# code to insert an object
// at the top of the Stack
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack of strings
        Stack<string> myStack = new Stack<string>();

        // Inserting the elements into the Stack
        myStack.Push("one");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements in the Stack are : ");
        Console.WriteLine(myStack.Count);

        myStack.Push("two");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements in the Stack are : ");
        Console.WriteLine(myStack.Count);

        myStack.Push("three");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements in the Stack are : ");
        Console.WriteLine(myStack.Count);

        myStack.Push("four");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements in the Stack are : ");
        Console.WriteLine(myStack.Count);

        myStack.Push("five");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements in the Stack are : ");
        Console.WriteLine(myStack.Count);

        myStack.Push("six");

        // Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements in the Stack are : ");
        Console.WriteLine(myStack.Count);
    }
}
```

## Output

```cs
Total number of elements in the Stack are : 1
Total number of elements in the Stack are : 2
Total number of elements in the Stack are : 3
Total number of elements in the Stack are : 4
Total number of elements in the Stack are : 5
Total number of elements in the Stack are : 6
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.stack-1.push?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.stack-1.push?view=netframework-4.7.2)