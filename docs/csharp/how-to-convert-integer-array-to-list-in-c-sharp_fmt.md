# 如何在 C# 中将整数数组转换为列表？

> 原文: [https://www.geeksforgeeks.org/how-to-convert-integer-array-to-list-in-c-sharp/](https://www.geeksforgeeks.org/how-to-convert-integer-array-to-list-in-c-sharp/)

我们已经给了一个整数数组 `arr`，任务是将整数数组转换成 C# 中的列表 `lst`。为了完成这个任务，我们有以下方法：

## 方法 1: `List<T>` 类

这个代表可以通过索引访问的对象列表。它属于 `System.Collections.Generic` 命名空间。`List<T>` 类还提供了搜索、排序和操作列表的方法。而这也是用来把一个给定的一个整数数组转换成列表的。

**语法:**

```cs
List<int> lst = new List<int> { 1, 2, 3}; 
```

**示例:**

```cs
// C# program to convert a 
// given an integer array 
// to the list
using System;
using System.Text;
using System.Collections.Generic;
using System.Linq;

public class GFG{

    static void Main(string[] args)
    {
        // given integer array 
        // { 10, 20, 30, 40, 50 }

        // using List<T> class
        List<int> lst = new List<int> { 10, 20, 30, 40, 50 };

          // you can write the above line of code as
          // int[] ints = new [] { 10, 20, 30, 40, 50 };
        // List<int> lst = ints.OfType<int>().ToList();

        // printing output
        foreach (int i in lst)
        {
          Console.Write(i + " ");
        }

    }
}
```

**输出:**

```cs
10 20 30 40 50 
```

## 方法 2: `List<T>(IEnumerable<T>)` 构造函数

使用此构造函数可以初始化 `List<T>` 类的新实例，该实例包含从指定集合中复制的元素，并且具有足够的容量来容纳复制的元素数量。因此这也可以用来将一个给定的整数数组转换为列表。

**语法:**

```cs
List<int> lst = new List<int>(integer_array); 
```

**示例:**

```cs
// C# program to convert a 
// given an integer array 
// to the list
using System;
using System.Text;
using System.Collections.Generic;
using System.Linq;

public class GFG{

    static List<int> get_list(int[] arr) 
    {
        // List<T>(IEnumerable<T>) 
        // Constructor
        // is a used to convert a 
        // given an integer array 
        // to the list

        List<int> L = new List<int> (arr);

        return L;
    }

    static void Main(string[] args)
    {
        // given integer array
        int[] arr = { 10, 20, 30, 40, 50 };

        // function calling
        List<int> lst = get_list(arr);

        // printing output
        foreach (int i in lst)
        {
          Console.Write(i + " ");
        }

    }
}
```

**输出:**

```cs
10 20 30 40 50 
```

## 方法 3: `AddRange(IEnumerable<T>)` 方法

此方法用于将指定集合的元素添加到列表 `List<T>` 的末尾。因此这也可以用来将一个给定的整数数组转换为列表。

**语法:**

```cs
List<int> lst = new List<int>();
lst.AddRange(integer_array) 
```

**示例:**

```cs
// C# program to convert a 
// given an integer array 
// to the list
using System;
using System.Text;
using System.Collections.Generic;
using System.Linq;

public class GFG{

    static List<int> get_list(int[] arr) 
    {
        // AddRange(IEnumerable<T>) 
        // Method is a used to convert
        // given an integer array 
        // to the list

        List<int> L = new List<int>();
        L.AddRange(arr);

        return L;
    }

    static void Main(string[] args)
    {
        // given integer array
        int[] arr = { 10, 20, 30, 40, 50 };

        // function calling
        List<int> lst = get_list(arr);

        // printing output
           foreach (int i in lst)
        {
          Console.Write(i + " ");
        }

    }
}
```

**输出:**

```cs
10 20 30 40 50 
```

## 方法 4: `ToList()` 方法

`Enumerable.ToList()` 方法来自 `System.Linq` 命名空间，它从 `IEnumerable<T>` 创建一个 `List<T>`。它返回一个包含输入序列元素的 `List<T>`。

**语法:**

```cs
List<int> lst = integer_array.ToList(); 
```

**示例:**

```cs
// C# program to convert a 
// given an integer array 
// to the list
using System;
using System.Text;
using System.Collections.Generic;
using System.Linq;

public class GFG{

    static List<int> get_list(int[] arr) 
    {
        // ToList() Method is a used 
        // to convert a given an 
        // integer array to the list

        List<int> L = arr.ToList();

        return L;
    }

    static void Main(string[] args)
    {
        // given integer array
        int[] arr = { 10, 20, 30, 40, 50 };

        // function calling
        List<int> lst = get_list(arr);

        // printing output
          foreach (int i in lst)
        {
          Console.Write(i + " ");
        }
    }
}
```

**输出:**

```cs
10 20 30 40 50 
```

## 方法 5: `Add()` 方法

此方法用于向列表末尾添加一个对象。因此这也可以用来将一个给定的整数数组转换成列表。

**语法:**

```cs
List<int> lst = new List<int>();
lst.Add(int val); 
```

**示例:**

```cs
// C# program to convert a 
// given an integer array 
// to the list
using System;
using System.Text;
using System.Collections.Generic;
using System.Linq;

public class GFG{

    static List<int> get_list(int[] arr) 
    {
        // Add() Method is a used 
        // to convert a given an 
        // integer array to the list

        List<int> L = new List<int>();

        for(int i = 0 ; i < arr.Length ; i++)
        {
            L.Add(arr[i]);
        }

        return L;
    }

    static void Main(string[] args)
    {
        // given integer array
        int[] arr = { 10, 20, 30, 40, 50 };

        // function calling
        List<int> lst = get_list(arr);

        // printing output
        foreach (int i in lst)
        {
          Console.Write(i + " ");
        }
    }
}
```

**输出:**

```cs
10 20 30 40 50 
```