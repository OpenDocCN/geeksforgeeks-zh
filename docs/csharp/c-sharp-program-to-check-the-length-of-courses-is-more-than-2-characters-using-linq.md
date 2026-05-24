# 使用 LINQ

检查课程长度是否超过 2 个字符的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-check-课程长度超过 2 个字符-使用-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-check-the-length-of-courses-is-more-than-2-characters-using-linq/)

给定一个数组，其中包含不同课程的列表，如“DSA”、“OS”、“JavaScript”等。现在我们的任务是在 LINQ 的帮助下检查给定数组中所有课程的长度是否超过 2 个字符。所以为了完成我们的任务，我们使用了 LINQ 的 All()方法。如果给定序列中的所有元素都满足指定条件，则此方法返回 true。否则，它将返回 false。

**语法:**

```cs
array_name.All(iterator => iterator.Length > 2)
```

其中 array_name 是输入数组，Length 是用于检查每门课程长度的函数。

**例:**

```cs
Input : { "cse", "it", "ft", "bio-tech", "chemical" }
Output : False

Input : { "cse", "ece", "bio-tech", "chemical" }
Output : True
```

## c#

```cs
// C# program to find the check the length of
// courses is more than 2 characters Using LINQ
using System;
using System.Linq;

class GFG{

static void Main(string[] args)
{

    // Create 5 courses
    string[] course1 = { "cse", "ece", "bio-tech", "chemical", "civil" };
    string[] course2 = { "DSA", "JS", "Kotlin", "C", "React" };

    // Checking the length of all courses 
    // is greater than 2 or not
    bool result1 = course1.All(display => display.Length > 2);
    bool result2 = course2.All(display => display.Length > 2);

    Console.WriteLine("Is the length of the courses " +
                      "is greater than 2 in course1?: " + result1);

    Console.WriteLine("Is the length of the courses " +
                      "is greater than 2 in course2?: " + result2);
}
}
```

**输出:**

```cs
Is the length of the courses is greater than 2 in course1?: True
Is the length of the courses is greater than 2 in course2?: False
```