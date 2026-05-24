# C# | 将堆栈复制到数组中

> 原文: [https://www.geeksforgeeks.org/c-sharp-copy-the-stack-to-an-array/](https://www.geeksforgeeks.org/c-sharp-copy-the-stack-to-an-array/)

`Stack<T>.CopyTo(T[], Int32)` 方法用于将 `Stack<T>` 复制到从指定数组索引开始的现有一维数组中。

## 属性

*   `Stack<T>` 的容量是 `Stack<T>` 可以容纳的元素数量。当元素被添加到 `Stack<T>` 中时，容量会根据需要通过重新分配自动增加。
*   如果 `Count` 小于 `Stack<T>` 的容量，`Push` 是一个 O(1) 操作。如果需要增加容量来容纳新元素，`Push` 将变成 O(n) 操作，其中 n 是 `Count`。`Pop` 是一个 O(1) 操作。
*   `Stack<T>` 接受 `null` 作为有效值，并允许重复元素。

## 语法

```cs
public void CopyTo (T[] array, int arrayIndex);
```

## 参数

*   `array`: 一维数组，是从 `Stack<T>` 复制的元素的目的地。数组必须具有从零开始的索引。
*   `arrayIndex`: 数组中开始复制的从零开始的索引。

## 异常

*   `ArgumentNullException`: 如果 `array` 为空。
*   `ArgumentOutOfRangeException`: 如果 `arrayIndex` 小于零。
*   `ArgumentException`: 源 `Stack<T>` 中的元素数量大于从 `arrayIndex` 到目标数组末尾的可用空间。

## 示例

下面给出了一些例子，以便更好地理解实现。

### 例 1

```cs
// C# code to Copy the Stack to an Array
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

        // Creating a string array arr
        string[] arr = new string[myStack.Count];

        // Copying the elements of stack into array arr
        myStack.CopyTo(arr, 0);

        // Displaying the elements in array arr
        foreach(string str in arr)
        {
            Console.WriteLine(str);
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

### 例 2

```cs
// C# code to Copy the Stack to an Array
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a Stack of Integers
        Stack<int> myStack = new Stack<int>();

        // Inserting the elements into the Stack
        myStack.Push(2);
        myStack.Push(3);
        myStack.Push(4);
        myStack.Push(5);
        myStack.Push(6);

        // Creating an Integer array arr
        int[] arr = new int[myStack.Count];

        // Copying the elements of stack into array arr
        myStack.CopyTo(arr, 0);

        // Displaying the elements in array arr
        foreach(int i in arr)
        {
            Console.WriteLine(i);
        }
    }
}
```

**输出:**

```cs
6
5
4
3
2
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.stack-1.copyto?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.stack-1.copyto?view=netframework-4.7.2)