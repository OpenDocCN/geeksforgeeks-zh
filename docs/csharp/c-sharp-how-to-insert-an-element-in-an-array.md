# C# |如何在数组中插入元素？

> 原文:[https://www . geeksforgeeks . org/c-sharp-如何在数组中插入元素/](https://www.geeksforgeeks.org/c-sharp-how-to-insert-an-element-in-an-array/)

[数组](https://www.geeksforgeeks.org/c-sharp-arrays/)是存储在连续存储位置的项目的集合。在本文中，我们将看到如何在 C# 中的数组中插入一个元素。

假设我们有一个数组，我们想在这个数组的特定位置插入一个元素。

下面是如何做到这一点。

1.  首先获取要插入的元素，比如 x
2.  然后得到这个元素要插入的位置，比如 pos
3.  创建一个大小比以前大一倍的新数组
4.  将前一个数组中的所有元素复制到新数组中，直到位置位置
5.  在位置插入元素 x
6.  将前一个数组中的剩余元素插入到 pos 之后的新数组中

```cs
// C# program to insert an 
// element in an array
using System;

public class GFG {

    // Main Method
    static public void Main()
    {

        int n = 10;
        int[] arr = new int[n];
        int i;

        // initial array of size 10
        for (i = 0; i < n; i++)
            arr[i] = i + 1;

        // print the original array
        for (i = 0; i < n; i++)
            Console.Write(arr[i] + " ");
        Console.WriteLine();

        // element to be inserted
        int x = 50;

        // position at which element 
        // is to be inserted
        int pos = 5;

        // create a new array of size n+1
        int[] newarr = new int[n + 1];

        // insert the elements from the 
        // old array into the new array
        // insert all elements till pos
        // then insert x at pos
        // then insert rest of the elements
        for (i = 0; i < n + 1; i++) {
            if (i < pos - 1)
                newarr[i] = arr[i];
            else if (i == pos - 1)
                newarr[i] = x;
            else
                newarr[i] = arr[i - 1];
        }

        // print the updated array
        for (i = 0; i < n + 1; i++)
            Console.Write(newarr[i] + " ");
        Console.WriteLine();
    }
}
```

**输出:**

```cs
1 2 3 4 5 6 7 8 9 10 
1 2 3 4 50 5 6 7 8 9 10

```