# C# |检查一个数组对象是否等于另一个数组对象

> 原文:[https://www . geesforgeks . org/c-sharp-check-如果一个数组对象等于另一个数组对象/](https://www.geeksforgeeks.org/c-sharp-check-if-an-array-object-is-equal-to-another-array-object/)

一个[数组](https://www.geeksforgeeks.org/c-sharp-arrays/)是一组相似类型的变量，它们被一个共同的名字所引用。每个数据项被称为数组的一个元素。**等于(对象)**方法由[数组类](https://www.geeksforgeeks.org/c-array-class/)从[对象类](https://www.geeksforgeeks.org/c-object-class/)继承而来，用于检查一个数组是否等于另一个数组。

**语法:**

```cs
public virtual bool Equals (object obj);
```

这里， *obj* 是要与当前对象进行比较的对象。

**返回值:**如果指定对象等于当前对象，则该方法返回*真*，否则返回*假*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to check if a Array is
// equal to other Array or not
using System;

namespace geeksforgeeks {

class GFG {

    // Main Method
    public static void Main()
    {

        // Two-dimensional array
        int[, ] intarray = new int[, ] { { 1, 2 },
                                         { 3, 4 },
                                         { 5, 6 },
                                         { 7, 8 } };

        // check if intarray is
        // equal to itself or not
        Console.WriteLine(intarray.Equals(intarray));
    }
}
}
```

**输出:**

```cs
True

```

**例 2:**

```cs
// C# code to check if an Array is
// equal to other Array or not
using System;

namespace geeksforgeeks {

class GFG {

    // Main Method
    public static void Main()
    {

        // Creating and intializing new the String
        String[] arr1 = new String[4] { "Sun", "Mon", "Tue", "Thu" };

        // taking anotther array
        String[] arr2 = new String[4] { "Sun", "Mon", "Tue", "Thu" };

        // check if arr1 is
        // equal to arr2 or not
        Console.WriteLine(arr1.Equals(arr2));

        // assigning arr1 reference to arr3
        String[] arr3 = new String[4];
        arr3 = arr1;

        // check if arr2 is
        // equal to arr3 or not
        Console.WriteLine(arr2.Equals(arr3));

        // check if arr1 is
        // equal to arr3 or not
        // it will return true as both 
        // array object refer to same
        Console.WriteLine(arr1.Equals(arr3));

    }
}
}
```

**输出:**

```cs
False
False
True

```

**注意:**如果当前实例是引用类型， *Equals(Object)方法*检查引用是否相等。