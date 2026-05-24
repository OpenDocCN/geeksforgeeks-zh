# C# | SortedDictionary。项目[]物业

> 原文:[https://www . geeksforgeeks . org/c-sharp-sorted dictionary-item-property/](https://www.geeksforgeeks.org/c-sharp-sorteddictionary-item-property/)

此属性用于获取或设置与指定键关联的值。

**语法:**

```cs
public TValue this[TKey key] { get; set; }
```

这里，*键*是要获取或设置的值的键。

**属性值:**与指定的*键*相关联的值。如果没有找到指定的*键*，一个 get 操作抛出一个 *KeyNotFoundException* ，一个 set 操作用指定的键创建一个新元素。

**异常:**

*   **参数空异常:**如果*键*为空。
*   **KeyNotFoundException:** 如果检索到属性并且集合中不存在*键*。

**示例:**

```cs
// C# code to get or set the value
// associated with the specified key
using System;
using System.Collections;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedDictionary named myDict
        SortedDictionary<string, string> myDict = 
          new SortedDictionary<string, string>();

        // Adding key/value pairs in myDict
        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // Displaying the key/value pairs in myDict
        foreach(KeyValuePair<string, string> k in myDict)
        {
            Console.WriteLine("Key = {0}, Value = {1}",
                              k.Key, k.Value);
        }

        // Displaying the value associated
        // with key "Russia"
        Console.Write("\nValue associated with Russia: ");
        Console.Write(myDict["Russia"]);

        // Setting the value associated with key "Russia"
        myDict["Russia"] = "Saint Petersburg";

        // Displaying the value associated
        // with key "Russia"
        Console.Write("\n\nValue associated with"+
                       " Russia After Setting: ");

        Console.Write(myDict["Russia"]);

        // Displaying the value associated
        // with key "India"
        Console.Write("\n\nValue associated with India: ");
        Console.Write(myDict["India"]);

        // Setting the value associated with key "India"
        myDict["India"] = "Mumbai";

        // Displaying the value associated
        // with key "India"
        Console.Write("\n\nValue associated "+
                "with India After Setting: ");

        Console.Write(myDict["India"]);
        Console.WriteLine("\n");

        // Displaying the key/value pairs in myDict
        foreach(KeyValuePair<string, string> k1 in myDict)
        {
            Console.WriteLine("Key = {0}, Value = {1}",
                              k1.Key, k1.Value);
        }
    }
}
```

**Output:**

```cs
Key = Australia, Value = Canberra
Key = Belgium, Value = Brussels
Key = China, Value = Beijing
Key = India, Value = New Delhi
Key = Netherlands, Value = Amsterdam
Key = Russia, Value = Moscow

Value associated with Russia: Moscow

Value associated with Russia After Setting: Saint Petersburg

Value associated with India: New Delhi

Value associated with India After Setting: Mumbai

Key = Australia, Value = Canberra
Key = Belgium, Value = Brussels
Key = China, Value = Beijing
Key = India, Value = Mumbai
Key = Netherlands, Value = Amsterdam
Key = Russia, Value = Saint Petersburg

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted dictionary-2 . item？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sorteddictionary-2.item?view=netframework-4.7.2)