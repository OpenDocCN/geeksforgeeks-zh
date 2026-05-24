# C# |将整个链表<t>复制到数组</t>

> 原文:[https://www . geeksforgeeks . org/c-sharp-copy-the-all-linked list to array/](https://www.geeksforgeeks.org/c-sharp-copy-the-entire-linkedlistt-to-array/)

**链接列表<T1**T9。CopyTo(T[]，Int32) 方法用于将整个*链表< **T** >* 复制到一个兼容的一维数组中，从目标数组的指定索引开始。

**语法:**

```cs
public void CopyTo (T[] array, int index);

```

**参数:**

*   **数组:**是一维数组，是从 LinkedList 复制的元素的目的地。数组必须具有从零开始的索引。
*   **索引:**是数组中从零开始复制的索引。

**异常:**

*   **ArgumentNullException :** 如果数组为空。
*   **argumentoutofrangerexception:**如果索引小于零。
*   **ArgumentException :** 如果源 LinkedList 中的元素数量大于从索引到目标数组末尾的可用空间。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to copy LinkedList to
// Array, starting at the specified
// index of the target array
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a LinkedList of Strings
        LinkedList<String> myList = new LinkedList<String>();

        // Adding nodes in LinkedList
        myList.AddLast("A");
        myList.AddLast("B");
        myList.AddLast("C");
        myList.AddLast("D");
        myList.AddLast("E");

        // Creating a string array
        string[] myArr = new string[1000];

        // Copying LinkedList to Array,
        // starting at the specified index
        // of the target array
        myList.CopyTo(myArr, 0);

        // Displaying elements in array myArr
        foreach(string str in myArr)
        {
            Console.WriteLine(str);
        }
    }
}
```

**输出:**

```cs
A
B
C
D
E

```

**例 2:**

```cs
// C# code to copy LinkedList to
// Array, starting at the specified
// index of the target array
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a LinkedList of Integers
        LinkedList<int> myList = new LinkedList<int>();

        // Adding nodes in LinkedList
        myList.AddLast(5);
        myList.AddLast(7);
        myList.AddLast(9);
        myList.AddLast(11);
        myList.AddLast(12);

        // Creating an Integer array
        int[] myArr = new int[100];

        // Copying LinkedList to Array,
        // starting at the specified index
        // of the target array
        // This should raise "ArgumentOutOfRangeException"
        // as index is less than 0
        myList.CopyTo(myArr, -2);

        // Displaying elements in array myArr
        foreach(int i in myArr)
        {
            Console.WriteLine(i);
        }
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:要求非负数。
> 参数名称:索引

**注:**

*   元素被复制到数组中的顺序与枚举器遍历链表的顺序相同。
*   这个方法是一个 **O(n)** 运算，其中 n 是 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . linked list-1 . copy to？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1.copyto?view=netframework-4.7.2)