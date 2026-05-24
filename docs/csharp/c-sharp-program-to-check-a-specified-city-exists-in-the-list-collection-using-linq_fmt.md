# 使用 LINQ

## 检查列表集合中存在指定城市的 C# 程序

> 原文: [https://www.geeksforgeeks.org/c-sharp-program-to-check-a-specified-city-exists-in-the-list-collection-using-linq/](https://www.geeksforgeeks.org/c-sharp-program-to-check-a-specified-city-exists-in-the-list-collection-using-linq/)

给定一个列表，我们需要使用 LINQ 检查给定列表中是否存在指定的城市。所以我们可以使用 `contains()` 方法来完成这个任务。此方法用于检查序列是否包含指定的元素。该方法以下列方式重载:

*   `Contains<TSource>(IEnumerable<TSource>, TSource)`: 用于使用默认的相等比较器检查指定的序列或列表是否包含给定的元素。
*   `Contains<TSource>(IEnumerable<TSource>, TSource, IEqualityComparer<TSource>)`: 使用指定的 `IEqualityComparer<T>` 检查指定的序列或列表是否包含给定的元素。

**语法:**

```cs
public static bool Contains<TSource>(this IEnumerable<TSource> my_list, TSource element);
```

**返回类型:** 返回类型为布尔型。如果列表中存在给定的元素，它将返回 `true`。否则，它将返回 `false`。

**示例:**

```cs
Input  : ["Mumbai", "Pune", "Bangalore", "Hyderabad"]
search_city : "Mumbai"
Output : True

Input  : ["Chennai", "Vizag", "Delhi"]
search_city : "Hyderabad"
Output : False
```

**方法:**

*   创建一个 `isPresent()` 方法，参数为城市列表和要搜索的城市名称。
*   在 `isPresent()` 方法中，使用 `contains()` 检查城市是否存在于列表中。

```cs
bool isExist = City_List.AsEnumerable().Contains(city);
```

如果这个城市存在，它将返回真，否则它将返回假。通过使用 `if` 条件检查它是真还是假并打印结果。

*   在主方法中，使用 `ArrayList` 创建一个城市名称列表。
*   调用 `isPresent()` 方法，参数为列表和我们想要检查是否存在的城市名称。

```cs
isPresent(City_List, "Mumbai");
```

## C# 代码

```cs
// C# program to check if the given city 
// is available in the list or not
using System;
using System.Collections.Generic;
using System.Linq;

class GFG{

    // Method to check the given city is present in the list or not
    static void isPresent(List<string> City_List, string city)
    {
        bool isExist = City_List.AsEnumerable().Contains(city);

        if (isExist)
            Console.WriteLine(city + " is present in list");
        else
            Console.WriteLine(city + " is not present in list");
    }

    // Driver code
    static void Main(string[] args)
    {

        // Creating a list
        List<string> City_List = new List<string>(){ "Mumbai", "Pune", 
                                                     "Bangalore", "Hyderabad" };

        // Calling method
        isPresent(City_List, "Mumbai");
        isPresent(City_List, "Chennai");
    }
}
```

**输出:**

```cs
Mumbai is present in list
Chennai is not present in list
```

**说明:** 在上面的例子中，首先我们创建了一个 `isPresent()` 方法。在这个方法中，我们使用 `contains()` 方法来检查城市是否出现在列表中，并将结果存储在 `isExist` 变量中。现在，当 `if` 语句为真时，它将返回“城市名称存在于列表中”，否则返回“城市名称不存在于列表中”。现在在主方法中，我们创建一个包含城市名称的列表，然后用城市列表和城市名称调用 `isPresent()` 方法，即 `isPresent(City_List, "Mumbai")` 和 `isPresent(City_List, "Chennai")`。由于第一个指定的城市名是孟买，并且它出现在列表中，所以它返回真，第二个指定的城市名是钦奈，它不在列表中，所以它返回假。