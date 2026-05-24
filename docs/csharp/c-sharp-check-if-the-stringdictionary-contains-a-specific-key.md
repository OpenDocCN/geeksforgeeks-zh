# C# |检查字符串是否包含特定的键

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-the-stringdictionary-contains-a-specific-key/](https://www.geeksforgeeks.org/c-sharp-check-if-the-stringdictionary-contains-a-specific-key/)

**StringDictionary。ContainsKey(String)** 方法用于**检查 StringDictionary 是否包含特定的键**。

**语法:**

```cs
public virtual bool ContainsKey (string key);

```

这里， ***键*** 是定位在字符串中的键。

**返回值:**如果 StringDictionary 包含指定键的条目，则该方法返回 ***true*** ，否则返回 ***false*** 。

**异常:**如果*键*为空，此方法将给出 ***参数为空异常*** 。

下面的程序说明了**字符串的使用。ContainsKey(String)** 方法:

**例 1:**

```cs
// C# code to check if the
// StringDictionary contains
// a specific key
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a StringDictionary named myDict
        StringDictionary myDict = new StringDictionary();

        // Adding key and value into the StringDictionary
        myDict.Add("G", "Geeks");
        myDict.Add("F", "For");
        myDict.Add("C", "C++");
        myDict.Add("DS", "Data Structures");
        myDict.Add("N", "Noida");

        // Checking if "DS" is contained in
        // StringDictionary myDict
        if (myDict.ContainsKey("DS"))
            Console.WriteLine("StringDictionary myDict contains the key");
        else
            Console.WriteLine("StringDictionary myDict does not contain the key");
    }
}
```

**输出:**

```cs
StringDictionary myDict contains the key

```

**例 2:**

```cs
// C# code to check if the
// StringDictionary contains
// a specific key
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a StringDictionary named myDict
        StringDictionary myDict = new StringDictionary();

        // Adding key and value into the StringDictionary
        myDict.Add("G", "Geeks");
        myDict.Add("F", "For");
        myDict.Add("C", "C++");
        myDict.Add("DS", "Data Structures");
        myDict.Add("N", "Noida");

        // Checking if "null" is contained in
        // StringDictionary myDict
        // This should raise "ArgumentNullException"
        // as the key is null
        if (myDict.ContainsKey(null))
            Console.WriteLine("StringDictionary myDict contains the key");
        else
            Console.WriteLine("StringDictionary myDict does not contain the key");
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentNullException:值不能为空。
> 参数名称:键

**注:**

*   该键以不区分大小写的方式处理，即在添加到字符串字典之前将其转换为小写。
*   这个方法是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string dictionary . contains key？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringdictionary.containskey?view=netframework-4.7.2)