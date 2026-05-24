# 如何计数 C# 数组中的元素？

> 原文:[https://www . geesforgeks . org/如何计算 c-sharp-array 中的元素数/](https://www.geeksforgeeks.org/how-to-count-elements-in-c-sharp-array/)

要计算 C# 数组中的元素数量，我们可以使用 IEnumerable 中的 **count()方法**。它包含在**T3 系统中。可枚举类。count 方法可以用于任何类型的集合，如数组、数组列表、列表、字典等。**

**语法:**

> 计数<tsource>()</tsource>

此方法返回数组中存在的元素总数。

> 计数<tsource>(功能<tsource boolean="">)</tsource></tsource>

此方法使用 Func 委托返回数组中与指定条件匹配的元素总数。

**示例 1:在数组中使用字符串值。**

在下面的代码块中，我们实现了计数函数来计算 C# 数组中的元素数量。首先，我们使用了系统。Linq，因为 count 函数位于这个类中，那么我们就创建了一个 count 变量来统计数组中的元素个数。之后，我们创建了一个包含 6 个元素的字符串数组。然后，我们在数组中使用了计数函数，并将结果计数存储到我们之前创建的计数变量中。然后用控制台。写行我们正在显示数组中元素的数量。

## C#

```cs
// C# program to illustrate the above concept
using System;
using System.Linq;

class GFG{

static public void Main()
{

    // Initializing count variable
    var totalCount = 0;

    // Creating an array of strings
    string[] elements = { "Rem", "Hisoka", "Gon", 
                          "Monkey D Luffy", "Alvida", 
                          "Shank" };

    // Invoking count function on the above elements
    totalCount = elements.Count();

    // Displaying the count
    Console.WriteLine(totalCount);
}
}
```

**Output**

```cs
6
```

**示例 2:在数组中使用整数值。**

## C#

```cs
// C# program to illustrate the above concept
using System;
using System.Linq;

class GFG{

static public void Main()
{

    // Creating a count variable
    var total = 0;

    // creating array of numbers
    int[] nums = { 9, 6, 5, 2, 1, 5, 8, 4,
                   6, 2, 3, 4, 8, 7, 5, 6 };

    // Counting the number of elements
    total = nums.Count();

    // Displaying the count
    Console.WriteLine(total);
}
}
```

**Output**

```cs
16
```

**示例 3:根据数组内的条件对特定元素进行计数。**

这里，在下面的程序中，我们正在创建一个颜色数组，然后使用计数方法，我们正在查找颜色“蓝色”在数组中出现的次数。然后显示计数。

## C#

```cs
// C# program to illustrate the above concept
using System;
using System.Linq;

class GFG{

static public void Main()
{

    // Creating a count variable
    var total = 0;

    // Creating an array of colors
    string[] colors = { "Red", "Blue", "Black",
                        "White", "Blue", "Blue" };

    // Counting the total number of time blue appears
    // in the array
    total = colors.Count(c => c == "Blue");

    // Displaying the count
    Console.WriteLine(total);
}
}
```

**输出:**

```cs
3
```