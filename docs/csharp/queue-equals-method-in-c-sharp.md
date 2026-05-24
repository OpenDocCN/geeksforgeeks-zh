# 排队。C# 中的 Equals()方法

> 原文:[https://www . geesforgeks . org/queue-equals-method-in-c-sharp/](https://www.geeksforgeeks.org/queue-equals-method-in-c-sharp/)

**等于(对象)方法**继承自[对象类](https://www.geeksforgeeks.org/c-sharp-object-class/)，用于检查指定的[队列类](https://www.geeksforgeeks.org/c-sharp-queue-class/)对象是否等于另一个队列类对象。这个方法属于`System.Collections`命名空间。

**语法:**

```cs
public virtual bool Equals (object obj);
```

这里， *obj* 是要与当前对象进行比较的对象。

**返回值:**如果指定对象等于当前对象，则该方法返回*真*，否则返回假。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to check if two Queue
// class objects are equal or not
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue named q1
        Queue q1 = new Queue();

        // Adding elements to q1
        q1.Enqueue(1);
        q1.Enqueue(2);
        q1.Enqueue(3);
        q1.Enqueue(4);

        // Checking whether q1 is
        // equal to itself or not
        Console.WriteLine(q1.Equals(q1));
    }
}
```

**Output:**

```cs
True

```

**例 2:**

```cs
// C# code to check if two Queue
// class objects are equal or not
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Queue named q1
        Queue q1 = new Queue();

        // Adding elements to the Queue
        q1.Enqueue("C");
        q1.Enqueue("C++");
        q1.Enqueue("Java");
        q1.Enqueue("C#");

        // Creating a Queue named q2
        Queue q2 = new Queue();

        q2.Enqueue("HTML");
        q2.Enqueue("CSS");
        q2.Enqueue("PHP");
        q2.Enqueue("SQL");

        // Checking whether q1 is
        // equal to q2 or not
        Console.WriteLine(q1.Equals(q2));

        // Creating a new Queue
        Queue q3 = new Queue();

        // Assigning q2 to q3
        q3 = q2;

        // Checking whether q3 is
        // equal to q2 or not
        Console.WriteLine(q3.Equals(q2));
    }
}
```

**Output:**

```cs
False
True

```