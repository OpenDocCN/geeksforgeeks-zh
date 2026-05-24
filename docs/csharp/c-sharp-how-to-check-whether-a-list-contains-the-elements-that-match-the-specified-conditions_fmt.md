# C# | 如何检查列表是否包含符合指定条件的元素

> 原文：[https://www.geeksforgeeks.org/c-sharp-how-to-check-whether-a-list-contains-the-elements-that-match-the-specified-conditions/](https://www.geeksforgeeks.org/c-sharp-how-to-check-whether-a-list-contains-the-elements-that-match-the-specified-conditions/)

`List<T>.Exists(Predicate<T>)`方法用于检查`List<T>`是否包含与指定谓词定义的条件相匹配的元素。

## 列表属性

*   它不同于数组。列表可以动态调整大小，但数组不能。
*   `List`类可以接受`null`作为引用类型的有效值，并且它还允许重复的元素。
*   如果`Count`等于`Capacity`，则列表的容量会通过重新分配内部数组而自动增加。在添加新元素之前，现有元素将被复制到新数组中。

## 语法

```cs
public bool Exists (Predicate<T> match);
```

## 参数

> `match`：是`Predicate<T>`委托，定义了要搜索的元素的条件。

## 返回值

如果`List<T>`包含一个或多个与指定谓词定义的条件匹配的元素，则该方法返回`true`，否则返回`false`。

## 异常

如果`match`为`null`，该方法将给出`ArgumentNullException`。

下面的程序说明了使用`List<T>.Exists(Predicate<T>)`方法：

## 例 1

```cs
// C# Program to check whether a List contains
// the elements that match the specified conditions
// defined by the predicate
using System;
using System.Collections;
using System.Collections.Generic;

class Geeks {

    // function which checks whether an
    // element is even or not. Or you can
    // say it is the specified condition
    private static bool isEven(int i)
    {
        return ((i % 2) == 0);
    }

    // Main Method
    public static void Main(String[] args)
    {

        // Creating an List<T> of Integers
        List<int> firstlist = new List<int>();

        // Adding elements to List
        for (int i = 1; i <= 10; i++) {
            firstlist.Add(i);
        }

        Console.WriteLine("Elements Present in List:\n");

        // Displaying the elements of List
        foreach(int k in firstlist)
        {
            Console.WriteLine(k);
        }

        Console.WriteLine(" ");

        Console.Write("Result: ");

        // Check the elements of firstlist that
        // match the conditions defined by predicate
        Console.WriteLine(firstlist.Exists(isEven));
    }
}
```

## 输出

```cs
Elements Present in List:

1
2
3
4
5
6
7
8
9
10
 
Result: True
```

## 例 2

```cs
// C# Program to check whether a List contains
// the elements that match the specified conditions
// defined by the predicate
using System;
using System.Collections;
using System.Collections.Generic;

class Geeks {

    // function which checks whether an
    // element is even or not. Or you can
    // say it is the specified condition
    private static bool isEven(int i)
    {
        return ((i % 2) == 0);
    }

    // Main Method
    public static void Main(String[] args)
    {

        // Creating an List<T> of Integers
        List<int> firstlist = new List<int>();

        // Adding elements to List
        firstlist.Add(5);
        firstlist.Add(7);
        firstlist.Add(9);
        firstlist.Add(11);
        firstlist.Add(3);
        firstlist.Add(17);
        firstlist.Add(19);

        Console.WriteLine("Elements Present in List:\n");

        // Displaying the elements of List
        foreach(int k in firstlist)
        {
            Console.WriteLine(k);
        }

        Console.WriteLine(" ");

        Console.Write("Result: ");

        // Check the elements of firstlist that
        // match the conditions defined by predicate
        Console.WriteLine(firstlist.Exists(isEven));
    }
}
```

## 输出

```cs
Elements Present in List:

5
7
9
11
3
17
19
 
Result: False
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.exists?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.exists?view=netframework-4.7.2)