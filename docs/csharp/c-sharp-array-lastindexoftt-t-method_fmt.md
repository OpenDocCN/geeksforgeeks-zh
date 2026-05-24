# C# Array.LastIndexOf<T>(T[], T) 方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-array-lastindexoftt-t-method/](https://www.geeksforgeeks.org/c-sharp-array-lastindexoftt-t-method/)

`Array.LastIndexOf<T>(T[], T)` 方法用于搜索指定的对象。它返回整个[数组](https://www.geeksforgeeks.org/c-array-class/)中最后一次出现的索引。

## 语法

```cs
public static int LastIndexOf<T>(T[] array, T value);
```

## 参数

- `array`: 是一个一维的、零索引的数组进行搜索。
- `value`: 返回上次出现的索引的元素。

## 返回值

返回 `System.Int32` 类型的从零开始的索引。整个 `array` 中最后一次出现的 `value` 的索引，否则返回 -1。

## 异常

如果 `array` 为 `null`，该方法将抛出 `ArgumentNullException`。

以下示例说明了上述方法的使用：

## 示例 1

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

## 示例 2

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
> System.ArgumentNullException: 值不能为空。
> 参数名称: array