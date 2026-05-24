# C# |如何对列表的每个元素执行指定的动作

> 原文：[https://www.geeksforgeeks.org/c-sharp-how-to-perform-a-specified-action-on-each-element-of-the-list/](https://www.geeksforgeeks.org/c-sharp-how-to-perform-a-specified-action-on-each-element-of-the-list/)

`List<T>.ForEach(Action<T>)`方法用于对`List<T>`中的每个元素执行指定的动作。

**列表属性:**

*   它不同于数组。列表可以动态调整大小，但数组不能。
*   `List`类可以接受`null`作为引用类型的有效值，并且它还允许重复的元素。
*   如果`Count`等于`Capacity`，则列表的容量会通过重新分配内部数组而自动增加。在添加新元素之前，现有元素将被复制到新数组中。

**语法:**

```cs
public void ForEach (Action<T> action);
```

**参数:**

> `action`：是`Action<T>`，代表对`List<T>`的每个元素执行的动作。

**异常:**

*   `ArgumentNullException`：如果`action`为`null`。
*   `InvalidOperationException`：如果集合中的元素已被修改。

下面的程序说明了使用`List<T>.ForEach(Action<T>)`方法：

**例 1:**

```cs
// C# Program to perform a specified
// action on each element of the List<T>
using System;
using System.Collections;
using System.Collections.Generic;

class Geeks {

    // display method
    static void display(string str)
    {
        Console.WriteLine(str);
    }

    // Main Method
    public static void Main(String[] args)
    {
        // Creating an List<T> of strings
        List<String> firstlist = new List<String>();

        // Adding elements to List
        firstlist.Add("Geeks");
        firstlist.Add("For");
        firstlist.Add("Geeks");
        firstlist.Add("GFG");
        firstlist.Add("C#");
        firstlist.Add("Tutorials");
        firstlist.Add("GeeksforGeeks");

        // using ForEach Method
        // which calls display method
        // on each element of the List
        firstlist.ForEach(display);
    }
}
```

**输出:**

```cs
Geeks
For
Geeks
GFG
C#
Tutorials
GeeksforGeeks
```

**例 2:**

```cs
// C# Program to perform a specified
// action on each element of the List<T>
using System;
using System.Collections;
using System.Collections.Generic;

class Geeks {

    // display method
    static void display(int str)
    {
        str = str + 5;
        Console.WriteLine(str);
    }

    // Main Method
    public static void Main(String[] args)
    {
        // Creating an List<T> of Integers
        List<int> firstlist = new List<int>();

        // Adding elements to List
        firstlist.Add(1);
        firstlist.Add(2);
        firstlist.Add(3);
        firstlist.Add(4);
        firstlist.Add(5);
        firstlist.Add(6);
        firstlist.Add(7);

        // using ForEach Method
        // which calls display method
        // on each element of the List
        firstlist.ForEach(display);
    }
}
```

**输出:**

```cs
6
7
8
9
10
11
12
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.foreach?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.foreach?view=netframework-4.7.2)