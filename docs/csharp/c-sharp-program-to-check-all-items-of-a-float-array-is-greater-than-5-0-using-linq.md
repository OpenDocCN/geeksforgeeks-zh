# 使用 LINQ

检查浮点数组所有项目大于 5.0 的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-check-all-items-of-a-float-array-is-大于-5-0-using-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-check-all-items-of-a-float-array-is-greater-than-5-0-using-linq/)

给定一个浮点数组，现在我们的任务是检查浮点数组中存在的所有元素是否都大于 5.0。所以我们用 LINQ 的 All()方法。此方法用于检查给定序列中的所有元素是否满足给定条件。如果指定序列的所有元素都通过了给定谓词的测试，它将返回 true，否则，它将返回 false。因此，为了解决给定的问题，我们使用以下查询:

> 结果= nums。全部(元素= >元素> 5.0F)；

这里，结果是存储最终结果的布尔类型变量，nums 是 float 的数组，All()方法包含检查给定数组中的每个元素是否满足条件的条件。这里，如果数组的所有元素都满足给定的条件，那么这个语句“nums。所有(元素= >元素> 5.0F)”将返回真。如果任何元素不满足给定的条件，那么它将返回 false。

**示例:**

```cs
Input  : [6.0, 7.89, 8.9, 89.5, 13.3]
Output : true

Input  : [2.0, 1.89, 2.9, 89.5, 13.3]
Output : false
```

**例 1:**

## C#

```cs
// C# program to check if all the items of a 
// Float Array is greater than 5.0
using System;
using System.Linq;

class geeks{

static void Main(string[] args)
{

    // Creating a float array
    float[] nums = { 1.2f, 30.3f, 5.6f, 7.0f, 10.1f };

    bool result;

    // Checking the given array contains all the
    // elements that are greate than 5.0
    result = nums.All(element => element > 5.0F);

    if (result == true)
    {
        Console.Write("Elements in the array are greater than 5");
    }
    else
    {
        Console.Write("Elements in the array are not greater than 5");
    }
}
}
```

**输出:**

```cs
Elements in the array are not greater than 5
```

**例 2:**

## C#

```cs
// C# program to check if all the items of a 
// Float Array is greater than 5.0
using System;
using System.Linq;

class geeks{

static void Main(string[] args)
{

    // Creating a float array
    float[] nums1 = { 1.2f, 30.3f, 3.6f, 7.0f, 10.1f };
    float[] nums2 = { 6.2f, 10.3f, 9.6f, 19.0f, 20.1f };

    bool result1, result2;

    // Checking the given array contains all the
    // elements that are greate than 5.0
    result1 = nums1.All(element => element > 5.0F);
    result2 = nums2.All(element => element > 5.0F);

    // Displaying the final result
    Console.WriteLine("Is nums1 contain all the elements " + 
                      "greater than 5.0f: " + result1);
    Console.WriteLine("Is nums2 contain all the elements " + 
                      "greater than 5.0f: " + result2);
}
}
```

**输出:**

```cs
Is nums1 contain all the elements greater than 5.0f: False
Is nums2 contain all the elements greater than 5.0f: True
```