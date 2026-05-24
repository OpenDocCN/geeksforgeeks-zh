# 排队。C# 中的 GetEnumerator 方法

> 原文:[https://www . geesforgeks . org/queue-get enumerator-method-in-c-sharp/](https://www.geeksforgeeks.org/queue-getenumerator-method-in-c-sharp/)

此方法返回遍历队列的枚举数。它属于*系统。集合*命名空间。

**语法:**

```cs
public virtual System.Collections.IEnumerator GetEnumerator ();
```

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to illustrate the 
// Queue.GetEnumerator Method 
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
        myq.Enqueue("E");
        myq.Enqueue("F");

        // To get an Enumerator
        // for the Queue
        IEnumerator enumerator = myq.GetEnumerator();

        // If MoveNext passes the end of the
        // collection, the enumerator is positioned
        // after the last element in the Queue
        // and MoveNext returns false.
        while (enumerator.MoveNext()) 
        {

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