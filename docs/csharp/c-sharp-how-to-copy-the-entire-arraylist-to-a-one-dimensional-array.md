# C# |如何将整个数组列表复制到一维数组中

> 原文:[https://www . geesforgeks . org/c-sharp-如何将整个数组列表复制到一维数组/](https://www.geeksforgeeks.org/c-sharp-how-to-copy-the-entire-arraylist-to-a-one-dimensional-array/)

**数组列表。复制方法**用于将整个[数组列表](https://www.geeksforgeeks.org/c-arraylist-class/)复制到兼容的一维数组中，从目标数组的开头开始。

**语法:**

```cs
public virtual void CopyTo (Array array);
```

这里，*数组*是一维数组，是从数组列表中复制的元素的目的地。数组必须具有从零开始的索引。

**异常:**

*   **参数空异常:**如果*数组*为空。
*   **参数异常:**如果*数组*是多维的 ***或*** ，则源数组列表中的元素数量大于目标*数组*可以包含的元素数量。
*   **InvalidCastException:** 如果源数组列表的类型不能自动转换为目标*数组的类型*。

以下程序说明了上述方法的使用:

**例 1:**

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

**输出:**

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

**例 2:**

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

**运行时错误:**

> 未处理异常:
> 系统。参数异常:目标数组不够长。检查目标索引和长度，以及数组的下限
> 参数名称:目标数组

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . copy to？view = net framework-4 . 7 . 2 # System _ Collections _ ArrayList _ copy to _ System _ Array _](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.copyto?view=netframework-4.7.2# System_Collections_ArrayList_CopyTo_System_Array_)