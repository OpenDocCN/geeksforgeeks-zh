# C# |字典。项目[]物业

> 原文:[https://www . geesforgeks . org/c-sharp-dictionary-item-property/](https://www.geeksforgeeks.org/c-sharp-dictionary-item-property/)

此属性用于获取或设置与字典中指定键相关联的值。

**语法:**

```cs
public TValue this[TKey key] { get; set; }
```

这里，*键*是要获取或设置的值的键。

**属性值:**是与指定键关联的值。如果找不到指定的键，get 操作抛出 *KeyNotFoundException* ，set 操作用指定的键创建新元素。

**异常:**

*   **ArgumentNullException** :如果密钥为空。
*   **KeyNotFoundException** :如果检索到属性并且集合中不存在*键*。

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

        // Creating a Dictionary named myDict
        Dictionary<string, string> myDict = new Dictionary<string, string>();

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
        Console.Write("\n\nValue associated with Russia After Setting: ");
        Console.Write(myDict["Russia"]);

        // Displaying the value associated
        // with key "India"
        Console.Write("\n\nValue associated with India: ");
        Console.Write(myDict["India"]);

        // Setting the value associated with key "India"
        myDict["India"] = "Mumbai";

        // Displaying the value associated
        // with key "India"
        Console.Write("\n\nValue associated with India After Setting: ");
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
Key = Netherlands, Value = Amsterdam
Key = China, Value = Beijing
Key = Russia, Value = Moscow
Key = India, Value = New Delhi

Value associated with Russia: Moscow

Value associated with Russia After Setting: Saint Petersburg

Value associated with India: New Delhi

Value associated with India After Setting: Mumbai

Key = Australia, Value = Canberra
Key = Belgium, Value = Brussels
Key = Netherlands, Value = Amsterdam
Key = China, Value = Beijing
Key = Russia, Value = Saint Petersburg
Key = India, Value = Mumbai

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . dictionary-2 . item？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.dictionary-2.item?view=netframework-4.7.2)