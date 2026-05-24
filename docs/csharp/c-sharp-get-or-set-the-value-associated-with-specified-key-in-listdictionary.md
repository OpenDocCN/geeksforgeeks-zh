# C# |获取或设置列表字典

中与指定键关联的值

> 原文:[https://www . geesforgeks . org/c-sharp-get-or-set-value-associated-in-specified-key-in-list dictionary/](https://www.geeksforgeeks.org/c-sharp-get-or-set-the-value-associated-with-specified-key-in-listdictionary/)

**列表词典。Item[Object]** 属性用于获取或设置与指定键关联的值。

**语法:**

```cs
public object this[object key] { get; set; }

```

这里， ***键*** 是要获取或设置其值的键。

**返回值:**与指定键关联的值。如果没有找到指定的密钥，试图获取它将返回**空值**，并试图使用指定的密钥创建一个新条目。

**异常:**如果*键*为空，该属性将给出 ***参数空异常*** 。

**示例:**

```cs
// C# code to get or set the value
// associated with the specified key
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a ListDictionary named myDict
        ListDictionary myDict = new ListDictionary();

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
*   这个方法是一个 O(n)运算，其中 n 是 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . list dictionary . item？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary.item?view=netframework-4.7.2)