# C# 中的 Stack.Count 属性

> 原文：[https://www.geeksforgeeks.org/stack-count-property-in-c-sharp/](https://www.geeksforgeeks.org/stack-count-property-in-c-sharp/)

该方法（属于 `System.Collections` 命名空间）用于获取堆栈中包含的元素数量。容量是堆栈可以存储的元素数量，计数是堆栈中实际存在的元素数量。容量始终大于或等于计数。检索该属性的值是一个 O(1) 操作。

## 语法

```cs
public virtual int Count { get; }
```

## 返回值

返回类型为 `System.Int32` 的堆栈中包含的元素数量。

以下程序说明了上述属性的使用：

## 示例 1

```cs
// C# code illustrate the
// Stack.Count Property
using System;
using System.Collections;

class GFG {

// Driver code
    public static void Main()
    {

// Creating a Stack
        Stack myStack = new Stack();

// Inserting the elements into the Stack
        myStack.Push("Chandigarh");
        myStack.Push("Delhi");
        myStack.Push("Noida");
        myStack.Push("Himachal");
        myStack.Push("Punjab");
        myStack.Push("Jammu");

// Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements"+
                         " in the Stack are : ");

Console.WriteLine(myStack.Count);
    }
}
```

**输出：**

```cs
Total number of elements in the Stack are : 6
```

## 示例 2

```cs
// C# code illustrate the
// Stack.Count Property
using System;
using System.Collections;

class GFG {

// Driver code
    public static void Main()
    {

// Creating a Stack
        Stack myStack = new Stack();

// Displaying the count of elements
        // contained in the Stack
        Console.Write("Total number of elements"+
                         " in the Stack are : ");

// The function should return 0
        // as the Stack is empty and it
        // doesn't contain any element
        Console.WriteLine(myStack.Count);
    }
}
```

**输出：**

```cs
Total number of elements in the Stack are : 0
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.stack.count?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.stack.count?view=netframework-4.7.2)