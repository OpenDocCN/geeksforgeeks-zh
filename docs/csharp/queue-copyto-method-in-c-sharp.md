# 排队。C# 中的 CopyTo()方法

> 原文:[https://www . geeksforgeeks . org/queue-copy to-method-in-c-sharp/](https://www.geeksforgeeks.org/queue-copyto-method-in-c-sharp/)

此方法用于将队列元素复制到现有的一维数组中，从指定的数组索引开始。元素被复制到数组中的顺序与枚举器遍历队列的顺序相同，这个方法是一个 O(n)操作，其中 n 是 Count。该方法属于`System.Collections`命名空间。

**语法:**

```cs
public virtual void CopyTo (Array array, int index);
```

**参数:**

> **数组:**一维[数组](https://www.geeksforgeeks.org/c-sharp-arrays/)是从 Queue 复制的元素的目的地。数组必须具有从零开始的索引。
> 
> **索引:**是数组中从零开始复制的索引。

**异常:**

*   **参数空异常:**如果*数组*为空。
*   **argumentoutofrangerexception:**如果*指数*小于零。
*   **参数异常:**如果数组是多维的`Or`源队列中的元素数量大于目标数组可以包含的元素数量。
*   **InvalidCastException:** 如果源队列的类型无法自动转换为目标数组的类型。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to illustrate the
// Queue.CopyTo(Array, Int32)
// Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an Queue
        Queue myq = new Queue();

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
        for (int i = 0; i < arr.Length; i++) {
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
        for (int i = 0; i < arr.Length; i++) {
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
// Queue.CopyTo(Array, Int32)
// Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an Queue
        Queue myq = new Queue();

        // Adding elements to Queue
        myq.Enqueue("A");
        myq.Enqueue("B");
        myq.Enqueue("C");
        myq.Enqueue("D");

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
> at(包装中柱)系统。Object.virt _ 石碑 ref_sealed_class(intptr，Object)

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . queue . copy to？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.queue.copyto?view=netframework-4.7.2)