# 叠加。C# 中的 Equals()方法

> 原文:[https://www . geesforgeks . org/stack-equals-method-in-c-sharp/](https://www.geeksforgeeks.org/stack-equals-method-in-c-sharp/)

**等于(对象)方法**从[对象类](https://www.geeksforgeeks.org/c-sharp-object-class/)继承而来，用于检查指定的[堆栈类](https://www.geeksforgeeks.org/c-sharp-stack-class/)对象是否等于另一个堆栈类对象。这个方法属于`System.Collections`命名空间。

**语法:**

```cs
public virtual bool Equals (object obj);
```

这里， *obj* 是要与当前对象进行比较的对象。

**返回值:**如果指定对象等于当前对象，则该方法返回*真*，否则返回假。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to check if two Stack
// class objects are equal or not
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack named st1
        Stack st1 = new Stack();

        // Adding elements to st1
        st1.Push(1);
        st1.Push(2);
        st1.Push(3);
        st1.Push(4);

        // Checking whether st1 is
        // equal to itself or not
        Console.WriteLine(st1.Equals(st1));
    }
}
```

**Output:**

```cs
True

```

**例 2:**

```cs
// C# code to check if two Stack
// class objects are equal or not
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Stack named st1
        Stack st1 = new Stack();

        // Adding elements to the Stack
        st1.Push("C");
        st1.Push("C++");
        st1.Push("Java");
        st1.Push("C#");

        // Creating a Stack named st2
        Stack st2 = new Stack();

        st2.Push("HTML");
        st2.Push("CSS");
        st2.Push("PHP");
        st2.Push("SQL");

        // Checking whether st1 is
        // equal to st2 or not
        Console.WriteLine(st1.Equals(st2));

        // Creating a new Stack
        Stack st3 = new Stack();

        // Assigning st2 to st3
        st3 = st2;

        // Checking whether st3 is
        // equal to st2 or not
        Console.WriteLine(st3.Equals(st2));
    }
}
```

**Output:**

```cs
False
True

```