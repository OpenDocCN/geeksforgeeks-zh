# 排序列表包含 C# 中的 Key()方法，并附有示例

> 原文:[https://www . geesforgeks . org/sorted list-contains key-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/sortedlist-containskey-method-in-c-sharp-with-examples/)

给定一个 SortedList 对象，现在我们的任务是检查给定的 SortedList 对象是否包含特定的键。所以做这个任务我们使用 **ContainsKey()** 方法。此方法用于确定 SortedList 对象是否包含特定的键。如果找到密钥，它将返回 true，否则，它将返回 false。

**语法:**

> bool SortedList。ContainsKey(对象密钥)；

键在排序列表对象中的位置。

**示例:**

```cs
Input  : [(1, "Python"), (2, "c")]
Key    : 1
Output : Found
Input  : [(1, "Python"), (2, "c")]
Key    : 4
Output : Not Found
```

**进场:**

> 1.  Create a sorted list.
> 2.  Add keywords and values to the sorted list.
> 3.  Use the ContainsKey () method to check whether a specific key exists in the list.
> 4.  Display output.

## C#

```cs
// C# program to check whether a SortedList 
// object contains a specific key or not
using System;
using System.Collections;

class GFG{

static public void Main()
{

    // Create sorted list
    SortedList data = new SortedList();

    // Add elements to data sorted list 
    data.Add(1, "Python");
    data.Add(2, "c");
    data.Add(3, "java");
    data.Add(4, "php");
    data.Add(5, "html");
    data.Add(6, "bigdata");
    data.Add(7, "java script");

    // Check whether the key - 1 is present
    // in the list or not
    if (data.ContainsKey(1))
        Console.WriteLine("Present in the List");
    else
        Console.WriteLine("Not in the List");

    // Check whether the key - 4 is present
    // in the list or not
    if (data.ContainsKey(4))
        Console.WriteLine("Present in the List");
    else
        Console.WriteLine("Not in the List");

    // Check whether the key - 8 is present
    // in the list or not
    if (data.ContainsKey(8))
        Console.WriteLine("Present in the List");
    else
        Console.WriteLine("Not in the List");
}
}
```

**输出:**

```cs
Present in the List
Present in the List
Not in the List
```