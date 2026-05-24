# C# |用指定的键获取或设置混合字典中的值

> 原文:[https://www . geesforgeks . org/c-sharp-get-or-set-value-in-hybrid dictionary-with-specified-key/](https://www.geeksforgeeks.org/c-sharp-gets-or-sets-the-value-in-hybriddictionary-with-specified-key/)

**杂交词典。Item[Object]** 属性用于获取或设置与指定键关联的值。

**语法:**

```cs
public object this[object key] { get; set; }

```

这里， ***键*** 是要获取或设置其值的键。

**返回值:**与指定键关联的值。如果没有找到指定的密钥，试图获取它将返回**空值**，并试图使用指定的密钥创建一个新条目。

**异常:**如果密钥为*空*，该属性将给出 ***参数空异常*** 。

以下程序说明了**混合词典的使用。项目[对象]** 属性:

**例 1:**

```cs
// C# code to get or set the value
// associated with the specified key
// in HybridDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HybridDictionary named myDict
        HybridDictionary myDict = new HybridDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // Displaying the key/value pairs in myDict
        foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " " + de.Value);
        }

        // Displaying the value associated
        // with key "Russia"
        Console.WriteLine(myDict["Russia"]);

        // Setting the value associated with key "Russia"
        myDict["Russia"] = "Saint Petersburg";

        // Displaying the value associated
        // with key "Russia"
        Console.WriteLine(myDict["Russia"]);

        // Displaying the value associated
        // with key "India"
        Console.WriteLine(myDict["India"]);

        // Setting the value associated with key "India"
        myDict["India"] = "Mumbai";

        // Displaying the value associated
        // with key "India"
        Console.WriteLine(myDict["India"]);

        // Displaying the key/value pairs in myDict
        foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " " + de.Value);
        }
    }
}
```

**输出:**

```cs
Australia Canberra
Belgium Brussels
Netherlands Amsterdam
China Beijing
Russia Moscow
India New Delhi
Moscow
Saint Petersburg
New Delhi
Mumbai
Australia Canberra
Belgium Brussels
Netherlands Amsterdam
China Beijing
Russia Saint Petersburg
India Mumbai

```

**注:**

*   此属性通过使用语法提供访问集合中特定元素的能力: **myCollection[key]** 。
*   一个键不能为**空**，但是一个值可以。
*   检索该属性的值是一个 O(1)操作。设置属性也是一个 O(1)操作。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . hybrid dictionary . item？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.hybriddictionary.item?view=netframework-4.7.2)