# C# |获取栈中包含的元素个数

> 原文：[https://www.geeksforgeeks.org/c-sharp-get-the-number-of-elements-contained-in-the-stack/](https://www.geeksforgeeks.org/c-sharp-get-the-number-of-elements-contained-in-the-stack/)

[栈](https://www.geeksforgeeks.org/stack-data-structure/)代表一个后进先出的集合对象。
`Stack<T>.Count`属性用于获取栈中包含的元素数量。检索该属性的值是一个O(1)操作。

## 语法

```cs
myStack.Count
```

这里`myStack`是`Stack<T>`的名字。

**返回值：** 属性返回`Stack<T>`中包含的元素数量。

## 例 1

```cs
// C# code to Get the number of
// elements contained in the Stack
using System;
using System.Collections.Generic;

class GFG {

// Driver code
    public static void Main()
    {

// Creating a Stack of strings
        Stack<string> myStack = new Stack<string>();

// Inserting the elements into the Stack
        myStack.Push("Chandigarh");
        myStack.Push("Delhi");
        myStack.Push("Noida");
        myStack.Push("Himachal");
        myStack.Push("Punjab");
        myStack.Push("Jammu");

// Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements in the Stack are : ");
        Console.WriteLine(myStack.Count);
    }
}
```

**Output:**

```cs
Total number of elements in the Stack are : 6
```

## 例 2

```cs
// C# code to Get the number of
// elements contained in the Stack
using System;
using System.Collections.Generic;

class GFG {

// Driver code
    public static void Main()
    {

// Creating a Stack of Integers
        Stack<int> myStack = new Stack<int>();

// Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements in the Stack are : ");

// The function should return 0
        // as the Stack is empty and it
        // doesn't contain any element
        Console.WriteLine(myStack.Count);
    }
}
```

**Output:**

```cs
Total number of elements in the Stack are : 0
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.stack.count?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.stack.count?view=netframework-4.7.2)