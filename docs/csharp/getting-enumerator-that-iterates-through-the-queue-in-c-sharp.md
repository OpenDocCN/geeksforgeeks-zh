# 获取在 C# 中遍历队列的枚举器

> 原文:[https://www . geeksforgeeks . org/get-enumerator-in-c-sharp-迭代队列/](https://www.geeksforgeeks.org/getting-enumerator-that-iterates-through-the-queue-in-c-sharp/)

**排队< T >。GetEnumerator 方法**用于获取一个可以遍历队列的枚举器。它属于*体系。集合.通用*命名空间。

**语法:**

```cs
public System.Collections.Generic.Queue<T>.Enumerator GetEnumerator ();
```

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to illustrate the
// Queue<T>.GetEnumerator Method
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an Queue of strings
        Queue<string> myq = new Queue<string>();

        // Adding elements to Queue
        myq.Enqueue("A");
        myq.Enqueue("B");
        myq.Enqueue("C");
        myq.Enqueue("D");
        myq.Enqueue("E");
        myq.Enqueue("F");

        // To get an Enumerator
        // for the Queue
        IEnumerator<string> enumerator = 
                    myq.GetEnumerator();

        // If MoveNext passes the end of the
        // collection, the enumerator is positioned
        // after the last element in the Queue
        // and MoveNext returns false.
        while (enumerator.MoveNext()) {

            Console.WriteLine(enumerator.Current);
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
F

```