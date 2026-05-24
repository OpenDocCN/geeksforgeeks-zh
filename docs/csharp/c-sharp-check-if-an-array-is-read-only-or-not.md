# C# |检查数组是否为只读

> 原文:[https://www . geeksforgeeks . org/c-sharp-check-如果一个数组是只读或非只读的/](https://www.geeksforgeeks.org/c-sharp-check-if-an-array-is-read-only-or-not/)

**阵列。IsReadOnly 属性**用于获取一个值，该值指示[数组](https://www.geeksforgeeks.org/c-sharp-arrays/)是否为只读。

**语法:**

```cs
public bool IsReadOnly { get; }
```

**属性值:**对于所有数组，该属性始终返回 *false* 。

以下程序说明了上述属性的使用:

**例 1:**

```cs
// C# program to illustrate
// IsReadOnly Property of
// Array class
using System;
namespace geeksforgeeks {

class GFG {

    // Main Method
    public static void Main()
    {

        // declares an 1D Array of string
        string[] topic;

        // assigning null to array
        topic = new string[] { null };

        // Here we check whether is
        // array of fixed size or not
        Console.WriteLine("Result: " + topic.IsReadOnly);
    }
}
}
```

**Output:**

```cs
Result: False

```

**例 2:**

```cs
// C# program to illustrate
// IsReadOnly Property of
// Array class
using System;
namespace geeksforgeeks {

class GFG {

    // Main Method
    public static void Main()
    {

        // Two-dimensional array 
        int[, ] arr = new int[, ] {{1, 2}, 
                                   {3, 4},  
                                   {5, 6},  
                                   {7, 8}}; 

        // Here we check whether is
        // array of fixed size or not
        Console.WriteLine("Result: " + arr.IsReadOnly);
    }
}
}
```

**Output:**

```cs
Result: False

```

**注:**

*   [数组](https://www.geeksforgeeks.org/c-array-class/)实现`[IsReadOnly](https://docs.microsoft.com/en-us/dotnet/api/system.array.isreadonly?view=netframework-4.7.2)` 属性是因为`System.Collections.IList`接口需要它。
*   只读数组不允许在创建数组后添加、移除或修改元素。
*   如果用户需要只读集合，那么他或她必须使用实现`System.Collections.IList`接口的`System.Collections`类。
*   如果用户将数组转换为 IList 接口对象，则`IList.IsReadOnly`属性返回 *false* 。但是，如果用户将一个数组转换为`IList<T> interface`，则 IsReadOnly 属性返回 true。
*   检索该属性的值是一个 O(1)操作。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . array . is readonly？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.isreadonly?view=netframework-4.7.2)