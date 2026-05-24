# C#
## 从哈希表中删除带有指定键的元素

> 原文：[https://www.geeksforgeeks.org/c-sharp-remove-the-element-with-the-specified-key-from-the-hashtable/](https://www.geeksforgeeks.org/c-sharp-remove-the-element-with-the-specified-key-from-the-hashtable/)

`哈希表`类表示基于键的哈希代码组织的`键和值对`的集合。该键用于访问集合中的项。`哈希表.Remove(object)`方法用于从哈希表中移除具有指定键的元素。

**语法：**

```cs
public virtual void Remove (object key);
```

**参数：**

> `键`：是`System.Object`类型的要移除的元素的键。

**异常：**

*   `ArgumentNullException`：如果`密钥`为空。
*   `NotSupportedException`：如果`哈希表`是只读的或具有固定的大小。

**示例：**

```cs
// C# code to remove the element
// with the specified key from Hashtable
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Hashtable
        Hashtable myTable = new Hashtable();

        // Adding elements in Hashtable
        myTable.Add("2", "Even & Prime");
        myTable.Add("3", "Odd & Prime");
        myTable.Add("4", "Even & non-prime");
        myTable.Add("9", "Odd & non-prime");

        // Print the number of entries in Hashtable
        Console.WriteLine("Total number of entries in Hashtable : " 
                          + myTable.Count);

        // To remove the elements from Hashtable
        // which has key as "3"
        myTable.Remove("3");

        // Print the number of entries in Hashtable
        Console.WriteLine("Total number of entries in Hashtable : " 
                          + myTable.Count);

        // To remove the elements from Hashtable
        // which has key as "4"
        myTable.Remove("4");

        // Print the number of entries in Hashtable
        Console.WriteLine("Total number of entries in Hashtable : " 
                          + myTable.Count);

        // Adding elements in Hashtable
        myTable.Add("g", "geeks");
        myTable.Add("c", "c++");
        myTable.Add("d", "data structures");

        // Print the number of entries in Hashtable
        Console.WriteLine("Total number of entries in Hashtable : " 
                          + myTable.Count);

        // To remove the elements from Hashtable
        // which has key as "c"
        myTable.Remove("c");

        // Print the number of entries in Hashtable
        Console.WriteLine("Total number of entries in Hashtable : " 
                          + myTable.Count);
    }
}
```

**输出：**

```cs
Total number of entries in Hashtable : 4
Total number of entries in Hashtable : 3
Total number of entries in Hashtable : 2
Total number of entries in Hashtable : 5
Total number of entries in Hashtable : 4
```

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.remove?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.remove?view=netframework-4.7.2)