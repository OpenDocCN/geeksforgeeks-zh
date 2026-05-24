# C# 如何将整个 ArrayList 复制到一维数组中

> 原文：[https://www.geeksforgeeks.org/c-sharp-how-to-copy-the-entire-arraylist-to-a-one-dimensional-array/](https://www.geeksforgeeks.org/c-sharp-how-to-copy-the-entire-arraylist-to-a-one-dimensional-array/)

`ArrayList.CopyTo` 方法用于将整个 `ArrayList` 复制到兼容的一维数组中，从目标数组的开头开始。

## 语法

```cs
public virtual void CopyTo (Array array);
```

这里，`array` 是一维数组，是从 `ArrayList` 中复制的元素的目的地。数组必须具有从零开始的索引。

## 异常

*   `ArgumentNullException`：如果 `array` 为 `null`。
*   `ArgumentException`：如果 `array` 是多维的，或者源 `ArrayList` 中的元素数量大于目标 `array` 可以包含的元素数量。
*   `InvalidCastException`：如果源 `ArrayList` 的类型不能自动转换为目标 `array` 的类型。

以下程序说明了上述方法的使用：

## 示例 1

```cs
// C# code to illustrate the
// ArrayList.CopyTo Method
using System;
using System.Collections;

class GFG {

// Driver code
    public static void Main()
    {

// Creating an ArrayList
        ArrayList myList = new ArrayList();

// Adding elements to ArrayList
        myList.Add("A");
        myList.Add("B");
        myList.Add("C");
        myList.Add("D");
        myList.Add("E");
        myList.Add("F");
        myList.Add("G");
        myList.Add("H");

// Creates and initializes the
        // one-dimensional target Array.
        String[] arr = new String[9];

        arr[0] = "C";
        arr[1] = "C++";
        arr[2] = "Java";
        arr[3] = "Python";
        arr[4] = "C#";
        arr[5] = "HTML";
        arr[6] = "CSS";
        arr[7] = "PHP";
        arr[8] = "DBMS";

        Console.WriteLine("Before CopyTo Method: ");

        Console.WriteLine("\nArrayList Contains: ");

// printing ArrayList elements
        foreach(Object obj in myList)
            Console.WriteLine("{0}", obj);

        Console.WriteLine("\nString Array Contains: ");

// printing String elements
        foreach(Object obj1 in arr)
            Console.WriteLine("{0}", obj1);

        Console.WriteLine("After CopyTo Method: ");

// using CopyTo Method to copy
        // the entire source ArrayList
        // to the target Array starting
        // at index 0
        myList.CopyTo(arr);

        Console.WriteLine("\nArrayList Contains: ");

// printing ArrayList elements
        foreach(Object obj in myList)
            Console.WriteLine("{0}", obj);

        Console.WriteLine("\nString Array Contains: ");

// printing String elements
        foreach(Object obj1 in arr)
            Console.WriteLine("{0}", obj1);
    }
}
```

### 输出

```cs
Before CopyTo Method:

ArrayList Contains:
A
B
C
D
E
F
G
H

String Array Contains:
C
C++
Java
Python
C#
HTML
CSS
PHP
DBMS

After CopyTo Method:

ArrayList Contains:
A
B
C
D
E
F
G
H

String Array Contains:
A
B
C
D
E
F
G
H
DBMS
```

## 示例 2

```cs
// C# code to illustrate the
// ArrayList.CopyTo Method
using System;
using System.Collections;

class GFG {

// Driver code
    public static void Main()
    {

// Creating an ArrayList
        ArrayList myList = new ArrayList();

// Adding elements to ArrayList
        myList.Add("HTML");
        myList.Add("CSS");
        myList.Add("PHP");
        myList.Add("DBMS");

// Creates and initializes the
        // one-dimensional target Array.
        // Here array size is only 2 i.e
        // it can hold only 3 elements.
        String[] arr = new String[2];

        Console.WriteLine("Before CopyTo Method: ");

        Console.WriteLine("\nArrayList Contains: ");

// printing ArrayList elements
        foreach(Object obj in myList)
            Console.WriteLine("{0}", obj);

        Console.WriteLine("\nString Array Contains: ");

// printing String elements
        foreach(Object obj1 in arr)
            Console.WriteLine("{0}", obj1);

        Console.WriteLine("After CopyTo Method: ");

// using CopyTo Method but It will give
        // Runtime Error as number of elements
        // in the source ArrayList is greater
        // than the number of elements that
        // the destination array can contain
        myList.CopyTo(arr);

        Console.WriteLine("\nArrayList Contains: ");

// printing ArrayList elements
        foreach(Object obj in myList)
            Console.WriteLine("{0}", obj);

        Console.WriteLine("\nString Array Contains: ");

// printing String elements
        foreach(Object obj1 in arr)
            Console.WriteLine("{0}", obj1);
    }
}
```

### 运行时错误

> 未处理异常：
> System.ArgumentException: 目标数组不够长。检查目标索引和长度，以及数组的下限。
> 参数名称: 目标数组

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.copyto?view=netframework-4.7.2#System_Collections_ArrayList_CopyTo_System_Array_](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.copyto?view=netframework-4.7.2#System_Collections_ArrayList_CopyTo_System_Array_)