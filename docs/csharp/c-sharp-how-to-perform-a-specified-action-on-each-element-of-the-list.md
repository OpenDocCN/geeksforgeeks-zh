# C# |如何对列表的每个元素执行指定的动作

> 原文:[https://www . geesforgeks . org/c-sharp-如何对列表中的每个元素执行指定的操作/](https://www.geeksforgeeks.org/c-sharp-how-to-perform-a-specified-action-on-each-element-of-the-list/)

**列表< T >。ForEach(动作< T >)方法**用于对列表< T >中的每个元素执行指定的动作。

**列表属性:**

*   它不同于数组。列表可以动态调整大小，但数组不能。
*   列表类可以接受 null 作为引用类型的有效值，并且它还允许重复的元素。
*   如果计数等于容量，则列表的容量会通过重新分配内部数组而自动增加。在添加新元素之前，现有元素将被复制到新数组中。

**语法:**

```cs
public void ForEach (Action action);

```

**参数:**

> **动作:**是< T >代表对列表< T >的每个元素执行的动作。

**异常:**

*   **ArgumentNullException:** 如果动作为空。
*   **无效操作异常:**如果集合中的元素已被修改。

下面的程序说明了使用**列表< T >。ForEach(动作< T >)方法:**

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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . foreach？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.foreach?view=netframework-4.7.2)