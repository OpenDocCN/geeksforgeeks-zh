# 检查指定类型是否为指针的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-check-a-specified-type-is-a-pointer-or-not/](https://www.geeksforgeeks.org/c-sharp-program-to-check-a-specified-type-is-a-pointer-or-not/)

指针是包含另一个变量引用的变量。或者换句话说，指针是一个存储同一类型变量地址的变量。例如，字符串指针可以存储字符串的地址。在 C# 中，我们可以通过使用 type 类的 IsPointer 属性来检查给定的类型是否是指针。如果指定的类型是指针，则此属性返回 true。否则，它将返回 false。它是只读属性。

**语法:**

```cs
public bool IsPointer{ get; }
```

**例 1:**

## C#

```cs
// C# program to check whether
// the given type is pointer or not
using System;
using System.Reflection;

class GFG{

static void Main()
{

    // Create an array with 5 elements of integer type
    int[] var1 = new int[5];
    string var2 = "GeeksforGeeks";
    float var3 = 3.45f;

    // Check the type is pointer or not
    // Using IsPointer property
    Console.WriteLine(var1.GetType().IsPointer);
    Console.WriteLine(var2.GetType().IsPointer);
    Console.WriteLine(var3.GetType().IsPointer);
}
}
```

**输出:**

```cs
False
False
False
```

**例 2:**

## C#

```cs
// C# program to check whether
// the given type is pointer or not
using System;
using System.Reflection;

class GFG{

static void Main()
{

    // Create an array of integer type with 7 elements
    int[] array1 = new int[7];

    // Check the type is pointer or not
    // Using IsPointer property
    if (array1.GetType().IsPointer == true)
    {
        Console.WriteLine("The given type is a pointer");
    }
    else
    {
        Console.WriteLine("The given type is not a pointer");
    }
}
}
```

**输出:**

```cs
The given type is not a pointer
```