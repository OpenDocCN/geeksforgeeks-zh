# 将队列元素复制到 C# 中的一维数组中

> 原文:[https://www . geesforgeks . org/copy-the-queue-elements-to-1-d-array-in-c-sharp/](https://www.geeksforgeeks.org/copying-the-queue-elements-to-1-d-array-in-c-sharp/)

**排队< T >。CopyTo(T[]，Int32)方法**用于从指定的数组索引开始，将队列元素复制到现有的一维数组中。元素被复制到数组中的顺序与枚举器遍历队列的顺序相同，这个方法是一个 O(n)操作，其中 n 是 Count。该方法属于`System.Collections.Generic`命名空间。

**语法:**

```cs
public void CopyTo (T[] array, int arrayIndex);
```

**参数:**

> **阵:**是一维[阵](https://www.geeksforgeeks.org/c-sharp-arrays/)，是从队列<复制过来的元素的目的地>。数组必须具有从零开始的索引。
> 
> **arrayIndex:** 是数组中从零开始复制的索引。

**异常:**

*   **参数空异常:**如果*数组*为空。
*   **argumentoutofrangerexception:**如果*指数*小于零。
*   **参数异常:**如果源队列< T >中的元素数量大于从*数组*到目的地*数组*末尾的可用空间。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to illustrate the
// Queue<T>.CopyTo(T[], Int32)
// Method
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an Queue of String
        Queue<string> myq = new Queue<string>();

        // Adding elements to Queue
        myq.Enqueue("A");
        myq.Enqueue("B");
        myq.Enqueue("C");
        myq.Enqueue("D");

        // Creates and initializes the
        // one-dimensional target Array.
        String[] arr = new String[6];

        // adding elements to Array
        arr[0] = "HTML";
        arr[1] = "PHP";
        arr[2] = "Java";
        arr[3] = "Python";
        arr[4] = "C#";
        arr[5] = "OS";

        Console.WriteLine("Before Method: ");

        Console.WriteLine("\nQueue Contains: ");

        // Displaying the elements in myq
        foreach(Object obj in myq)
        {
            Console.WriteLine(obj);
        }

        Console.WriteLine("\nArray Contains: ");

        // Displaying the elements in arr
        for (int i = 0; i < arr.Length; i++) 
        {
            Console.WriteLine("arr[{0}] : {1}", i, arr[i]);
        }

        Console.WriteLine("After Method: ");

        // Copying the entire source Queue
        // to the target Array starting at
        // index 2.
        myq.CopyTo(arr, 2);

        Console.WriteLine("\nQueue Contains: ");

        // Displaying the elements in myq
        foreach(Object obj in myq)
        {
            Console.WriteLine(obj);
        }

        Console.WriteLine("\nArray Contains: ");

        // Displaying the elements in arr
        for (int i = 0; i < arr.Length; i++) 
        {
            Console.WriteLine("arr[{0}] : {1}", i, arr[i]);
        }
    }
}
```

**输出:**

```cs
Before Method: 

Queue Contains: 
A
B
C
D

Array Contains: 
arr[0] : HTML
arr[1] : PHP
arr[2] : Java
arr[3] : Python
arr[4] : C#
arr[5] : OS
After Method: 

Queue Contains: 
A
B
C
D

Array Contains: 
arr[0] : HTML
arr[1] : PHP
arr[2] : A
arr[3] : B
arr[4] : C
arr[5] : D

```

**例 2:**

```cs
// C# code to illustrate the
// Queue<T>.CopyTo(T[], Int32)
// Method
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an Queue of String
        Queue<string> myq = new Queue<string>();

        // Adding elements to Queue
        myq.Enqueue("GFG");
        myq.Enqueue("Geeks");
        myq.Enqueue("Sudo");
        myq.Enqueue("DSA");

        // Creates and initializes the
        // one-dimensional target Array.
        String[] arr = new String[2];

        // adding elements to Array
        arr[0] = "HTML";
        arr[1] = "PHP";
        arr[2] = "Java";
        arr[3] = "Python";
        arr[4] = "C#";
        arr[5] = "OS";

        Console.WriteLine("Before Method: ");

        Console.WriteLine("\nQueue Contains: ");

        // Displaying the elements in myq
        foreach(Object obj in myq)
        {
            Console.WriteLine(obj);
        }

        Console.WriteLine("\nArray Contains: ");

        // Displaying the elements in arr
        for (int i = 0; i < arr.Length; i++) {
            Console.WriteLine("arr[{0}] : {1}", i, arr[i]);
        }

        Console.WriteLine("After Method: ");

        // using Method but It will give
        // Runtime Error as number of elements
        // in the source Queue is greater
        // than the number of elements that
        // the destination array can contain
        myq.CopyTo(arr, 2);

        Console.WriteLine("\nQueue Contains: ");

        // Displaying the elements in myq
        foreach(Object obj in myq)
        {
            Console.WriteLine(obj);
        }

        Console.WriteLine("\nArray Contains: ");

        // Displaying the elements in arr
        for (int i = 0; i < arr.Length; i++) {
            Console.WriteLine("arr[{0}] : {1}", i, arr[i]);
        }
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。IndexOutOfRangeException:索引超出了数组的界限。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . queue-1 . copy to？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1.copyto?view=netframework-4.7.2)