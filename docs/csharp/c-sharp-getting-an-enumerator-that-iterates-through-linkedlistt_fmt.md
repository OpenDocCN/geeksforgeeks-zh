# C# |获取遍历链表的枚举器

> 原文：[https://www.geeksforgeeks.org/c-sharp-getting-an-enumerator-that-iterates-through-linkedlistt/](https://www.geeksforgeeks.org/c-sharp-getting-an-enumerator-that-iterates-through-linkedlistt/)

## `LinkedList<T>.GetEnumerator` 方法
`LinkedList<T>.GetEnumerator` 方法用于获取遍历 `LinkedList<T>` 的枚举器。

## 语法
```cs
public System.Collections.Generic.LinkedList<T>.Enumerator GetEnumerator ();
```

## 返回值
为 `LinkedList<T>` 返回 `LinkedList<T>.Enumerator`。

以下程序说明了上述方法的使用：

## 例 1
```cs
// C# code to get an enumerator that
// iterates through the LinkedList<T>
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a LinkedList of Integers
        LinkedList<int> myList = new LinkedList<int>();

        // Adding nodes in LinkedList
        myList.AddLast(2);
        myList.AddLast(4);
        myList.AddLast(6);
        myList.AddLast(8);

        // To get an Enumerator
        // for the List.
        LinkedList<int>.Enumerator em = myList.GetEnumerator();
        display(em);
    }

    // display method
    static void display(IEnumerator<int> em)
    {
        while (em.MoveNext()) {
            int val = em.Current;
            Console.WriteLine(val);
        }
    }
}
```

## 输出
```cs

```

## 例 2
```cs
// C# code to get an enumerator that
// iterates through the LinkedList<T>
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a LinkedList of Strings
        LinkedList<String> myList = new LinkedList<String>();

        // Adding nodes in LinkedList
        myList.AddLast("GeeksforGeeks");
        myList.AddLast("GFG");
        myList.AddLast("Data Structures");
        myList.AddLast("Noida");

        // To get an Enumerator
        // for the LinkedList<T>.
        LinkedList<string>.Enumerator em = myList.GetEnumerator();
        display(em);
    }

    // display method
    static void display(IEnumerator<string> em)
    {
        while (em.MoveNext()) {
            string val = em.Current;
            Console.WriteLine(val);
        }
    }
}
```

## 输出
```cs
GeeksforGeeks
GFG
Data Structures
Noida
```

## 注
*   C# 语言的 `foreach` 语句隐藏了枚举器的复杂性。因此，建议使用 `foreach`，而不是直接操作枚举器。
*   枚举数可用于读取集合中的数据，但不能用于修改基础集合。
*   `Current` 返回同一对象，直到调用 `MoveNext` 或 `Reset` 为止。`MoveNext` 将 `Current` 设置为下一个元素。
*   只要集合保持不变，枚举数就保持有效。如果对集合进行了更改，例如添加、修改或删除元素，枚举数将无法恢复地失效，并且其行为未定义。
*   这个方法是一个 O(1) 运算。

## 参考
*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1.getenumerator?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1.getenumerator?view=netframework-4.7.2)