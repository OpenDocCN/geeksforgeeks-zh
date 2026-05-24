# C# |检查字符串是否包含特定值

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-the-stringdictionary-contains-a-specific-value/](https://www.geeksforgeeks.org/c-sharp-check-if-the-stringdictionary-contains-a-specific-value/)

**StringDictionary。ContainsValue(String)** 方法用于**检查 StringDictionary 是否包含特定值**。

**语法:**

```cs
public virtual bool ContainsValue (string value);

```

这里， ***值*** 是字符串中要定位的值。该值可以为空。

**返回值:**如果 StringDictionary 包含指定值的元素，则返回 ***true*** ，否则返回 ***false*** 。

下面的程序说明了**字符串的使用。ContainsValue(String)** 方法:

**例 1:**

```cs
// C# code to check if the
// StringDictionary contains
// a specific value
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

    // Checking if "C++" is contained in
    // StringDictionary myDict
    if (myDict.ContainsValue("C++"))
        Console.WriteLine("StringDictionary myDict contains the value");
    else
        Console.WriteLine("StringDictionary myDict does not contain the value");
    }
}
```

**Output:**

```cs
StringDictionary myDict contains the value

```

**例 2:**

```cs
// C# code to check if the
// StringDictionary contains
// a specific value
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
    // It should not raise any exception
    if (myDict.ContainsValue(null))
        Console.WriteLine("StringDictionary myDict contains the value");
    else
        Console.WriteLine("StringDictionary myDict does not contain the value");
    }
}
```

**Output:**

```cs
StringDictionary myDict does not contain the value

```

**注:**

*   使用[对象将字符串的元素值与指定值进行比较。等于](https://docs.microsoft.com/en-us/dotnet/api/system.object.equals?view=netframework-4.7.2)法。
*   这个方法是一个 O(n)运算，其中 n 是 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string dictionary . contains value？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringdictionary.containsvalue?view=netframework-4.7.2)