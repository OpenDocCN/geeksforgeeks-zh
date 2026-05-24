# C# | 为列表创建只读包装

> 原文：[https://www.geeksforgeeks.org/c-sharp-creating-a-read-only-wrapper-for-list/](https://www.geeksforgeeks.org/c-sharp-creating-a-read-only-wrapper-for-list/)

## `List<T>.AsReadOnly` 方法
`List<T>.AsReadOnly` 方法用于获取当前集合的只读 `ReadOnlyCollection<T>` 包装器。

## 语法
```cs
public System.Collections.ObjectModel.ReadOnlyCollection<T> AsReadOnly();
```

## 返回值
返回一个对象，该对象作为当前 `List<T>` 的只读包装器。

## 示例
```cs
// C# code to create a read-only
// wrapper for the List<T>
using System;
using System.Collections.Generic;

class GFG {

// Driver code
    public static void Main()
    {

// Creating an List<T> of Integers
        List<int> mylist = new List<int>();

// Adding elements to List
        mylist.Add(17);
        mylist.Add(19);
        mylist.Add(21);
        mylist.Add(9);
        mylist.Add(75);
        mylist.Add(19);
        mylist.Add(73);

Console.WriteLine("Before Wrapping: ");

// Displaying the elements
        // in the mylist
        foreach(int i in mylist)
        {
            Console.WriteLine(i);
        }

// Creating a Read-Only packing
        // around the List
        IList<int> readlist = mylist.AsReadOnly();

Console.WriteLine("After Wrapping: ");

// Displaying the elements
        // of Read-Only Collection
        foreach(int j in readlist)
        {
            Console.WriteLine(j);
        }

// You can add elements to
        // the original List i.e. mylist
        Console.WriteLine("Adding new element to mylist: ");
        mylist.Add(35);

// Displaying the elements
        // in the mylist
        foreach(int k in mylist)
        {
            Console.WriteLine(k);
        }

// But you cannot add elements
        // into the Read-Only Collection
        Console.WriteLine("Trying to add new element into readlist:");

// it will give error
        readlist.Add(34);

}
}
```

## 输出
```cs
Before Wrapping:
17
19
21
9
75
19
73
After Wrapping:
17
19
21
9
75
19
73
Adding new element to mylist:
17
19
21
9
75
19
73
35
Trying to add new element into readlist:
```

## 运行时错误
> 未处理异常:
> `System.NotSupportedException`: 集合是只读的。

## 参考
*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.asreadonly?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.asreadonly?view=netframework-4.7.2)