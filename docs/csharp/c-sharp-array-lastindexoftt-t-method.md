# C# |数组。 <t>(T[]，T)方法</t>

的最后索引

> 原文:[https://www . geesforgeks . org/c-sharp-array-last indexoft-t-method/](https://www.geeksforgeeks.org/c-sharp-array-lastindexoftt-t-method/)

***阵。< T > (T[]，T)方法*** 用于搜索指定的对象。它返回整个[数组](https://www.geeksforgeeks.org/c-array-class/)中最后一次出现的索引。

**语法:**

```cs
public static int LastIndexOf<T>(T[] array, T value);
```

**参数:**

> **数组**:是一个一维的，零索引的数组进行搜索。
> **值**:返回上次出现的索引的元素。

**返回值:**返回 System 类型的从零开始的索引。整个*数组*中最后一次出现的值的 Int32，否则返回-1。
**异常**如果*数组*为空，该方法将给出 ArgumentNullException。
以下示例说明了上述方法的使用:
**示例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Array.LastIndexOf<T>(T[], value<T>)
// Method
using System;

class Geeks {

    // Main Method
    public static void Main()
    {

        // Creates and initializes a new
        // Array with three elements of the
        // same value.
        string[] str = {"C", "C++", "C#", "Java",
                          "Python", "C#", "C++",
                                     "C#", "CSS"};

        // printing the Elements of an Array
        Console.WriteLine("Elements of Array: ");
        Console.WriteLine();
        foreach(string str1 in str)
        {
            Console.WriteLine(str1);
        }

        Console.Write("\nLast Occurrence of C# : ");

        // printing the last index of C#
        // using Array.LastIndexOf<T>(T[],
        // value<T>) Method
        Console.Write(Array.LastIndexOf(str, "C#"));

        Console.Write("\nLast Occurrence of C++: ");

        // printing the last index of C++
        // using Array.LastIndexOf<T>(T[],
        // value<T>) Method
        Console.Write(Array.LastIndexOf(str, "C++"));
    }
}
```

**输出:**

```cs
Elements of Array: 

C
C++
C#
Java
Python
C#
C++
C#
CSS

Last Occurrence of C# : 7
Last Occurrence of C++: 6
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Array.LastIndexOf<T>(T[], value<T>)
// Method
using System;

class Geeks {

    // Main Method
    public static void Main()
    {

        // creating and initializing an array
        int[] arr = {1, 2, 3, 4, 1, 2,
                       3, 4, 2, 4, 2};

        // printing the Elements of an Array
        Console.WriteLine("Elements of Array: ");
        Console.WriteLine();
        foreach(int i in arr)
        {
            Console.WriteLine(i);
        }

        // using Array.LastIndexOf<T>(T[],
        // value<T>) Method
        // it will give runtime error as
        // array parameter is null
        Console.Write(Array.LastIndexOf(null, 1));

    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentNullException:值不能为空。
> 参数名称:数组