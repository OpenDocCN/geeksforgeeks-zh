# C# |检查数组是否有固定大小

> 原文:[https://www . geesforgeks . org/c-sharp-check-如果一个阵列有固定大小或没有固定大小/](https://www.geeksforgeeks.org/c-sharp-check-if-an-array-has-fixed-size-or-not/)

**阵列。**用于获取一个指示数组是否有固定大小的值。该属性实现`[IList.IsFixedSize](https://docs.microsoft.com/en-us/dotnet/api/system.collections.ilist.isfixedsize?view=netframework-4.7.2# System_Collections_IList_IsFixedSize)` 属性。

**语法:**

```cs
public bool IsFixedSize { get; }
```

**属性值:**该属性对于所有数组始终返回*真*。

以下程序说明了上述属性的使用:

**例 1:**

```cs
// C# program to illustrate
// IsFixedSize of Array class
using System;
namespace geeksforgeeks {

class GFG {

    // Main Method
    public static void Main()
    {

        // declares an 1D Array of string
        string[] topic;

        // allocating memory for topic.
        topic = new string[] {"Array, ", "String, ",
                               "Stack, ", "Queue, ",
                        "Exception, ", "Operators"};

        // Displaying Elements of the array
        Console.WriteLine("Topic of C# :");

        foreach(string ele in topic)
            Console.WriteLine(ele + " ");

        Console.WriteLine();

        // Here we check whether is
        // array of fixed size or not
        Console.WriteLine("Result: " + topic.IsFixedSize);
    }
}
}
```

**Output:**

```cs
Topic of C# :
Array,  
String,  
Stack,  
Queue,  
Exception,  
Operators 

Result: True

```

**例 2:**

```cs
// C# program to illustrate
// IsFixedSize of Array class
using System;
namespace geeksforgeeks {

class GFG {

    // Main Method
    public static void Main()
    {

        // declares a 1D Array of string 
        // and assigning null to it
        string[] str = new string[] {null};

        // Here we check whether is
        // array of fixed size or not
        Console.WriteLine("Result: " + str.IsFixedSize);
    }
}
}
```

**Output:**

```cs
Result: True

```

**注:**

*   数组实现*是固定大小*属性，因为它是`System.Collections.IList`接口所需要的。
*   具有固定大小的数组不允许在创建数组后添加或移除元素，但允许修改现有元素。
*   检索该属性的值是一个 O(1)操作。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . array . isfixedsize？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.isfixedsize?view=netframework-4.7.2)