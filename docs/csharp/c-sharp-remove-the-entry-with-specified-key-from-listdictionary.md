# C# |从列表字典

中删除指定键的条目

> 原文:[https://www . geeksforgeeks . org/c-sharp-从列表字典中删除带有指定键的条目/](https://www.geeksforgeeks.org/c-sharp-remove-the-entry-with-specified-key-from-listdictionary/)

**列表词典。移除(对象)**方法用于从列表字典中移除具有指定键的条目。

**语法:**

```cs
public void Remove (object key);

```

这里，*键*是要删除的条目的键。

**异常:**如果密钥为空，该方法将给出 *ArgumentNullException* 。

下面是举例说明**列表词典的使用。移除(对象)方法**:

**例 1:**

```cs
// C# code to remove the entry with
// the specified key from the ListDictionary
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

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs in myDict are : " 
                                                  + myDict.Count);

        // Displaying the key/value pairs in myDict
        Console.WriteLine("The key/value pairs in myDict are : ");

        foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " " + de.Value);
        }

        // Remove the entry with the specified
        // key from the ListDictionary
        myDict.Remove("Russia");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs in myDict are : " 
                                                 + myDict.Count);

        // Displaying the key/value pairs in myDict
        Console.WriteLine("The key/value pairs in myDict are : ");

        foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " " + de.Value);
        }
    }
}
```

**输出:**

```cs
Total key/value pairs in myDict are : 6
The key/value pairs in myDict are : 
Australia Canberra
Belgium Brussels
Netherlands Amsterdam
China Beijing
Russia Moscow
India New Delhi
Total key/value pairs in myDict are : 5
The key/value pairs in myDict are : 
Australia Canberra
Belgium Brussels
Netherlands Amsterdam
China Beijing
India New Delhi

```

**例 2 :**

```cs
// C# code to remove the entry with
// the specified key from the ListDictionary
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
        myDict.Add("I", "first");
        myDict.Add("II", "second");
        myDict.Add("III", "third");
        myDict.Add("IV", "fourth");
        myDict.Add("V", "fifth");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs in myDict are : " 
                                                  + myDict.Count);
        // Displaying the key/value pairs in myDict

        Console.WriteLine("The key/value pairs in myDict are : ");

        foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " " + de.Value);
        }

        // Remove the entry with the specified
        // key from the ListDictionary
        // This should raise "ArgumentNullException"
        // as the key is null
        myDict.Remove(null);

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs in myDict are : " 
                                                  + myDict.Count);

        // Displaying the key/value pairs in myDict

        Console.WriteLine("The key/value pairs in myDict are : ");

        foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " " + de.Value);
        }
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentNullException:键不能为空。
> 参数名称:键

**注:**

*   如果列表字典不包含具有指定键的元素，则列表字典保持不变。不会引发异常。
*   这个方法是一个 O(n)运算，其中 n 是 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . list dictionary . remove？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary.remove?view=netframework-4.7.2)