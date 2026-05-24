# C# |获取或设置 StringDictionary 中指定键的值

> 原文:[https://www . geesforgeks . org/c-sharp-get-or-set-value-at-specified-in-stringdictionary/](https://www.geeksforgeeks.org/c-sharp-gets-or-sets-the-value-at-the-specified-key-in-stringdictionary/)

***StringDictionary。项[字符串]属性*** 用于获取或设置与指定键关联的值。

**语法:**

```cs
public virtual string this[string key] { get; set; }
```

这里*键*是*系统类型的键。字符串*的值是获取还是设置。

**返回值:**该属性返回与指定键关联的值。如果没有找到指定的键，Get 返回 *null* ，Set *用指定的键创建一个新的条目*。

**异常:**如果*键*为空，该属性抛出`ArgumentNullException` 。

以下程序说明了上述属性的使用:

**例 1:**

```cs
// C# code to get or set the value at
// the specified key in StringDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a StringDictionary named my1
        StringDictionary my1 = new StringDictionary();

        // Adding key and value into the StringDictionary
        my1.Add("1", "C");
        my1.Add("2", "C++");
        my1.Add("3", "Java");
        my1.Add("4", "Python");
        my1.Add("5", "C#");

        // Displaying the keys and
        // values in StringDictionary
        foreach(DictionaryEntry d in my1)
        {
            Console.WriteLine(d.Key + " " + d.Value);
        }

        Console.WriteLine("\nAfter Item[String] Property: \n");

        // setting the value at key 2
        my1["2"] = "HTML";

        // Displaying the keys and
        // values in StringDictionary
        foreach(DictionaryEntry d1 in my1)
        {
            Console.WriteLine(d1.Key + " " + d1.Value);
        }
    }
}
```

**输出:**

```cs
3 Java
5 C#
4 Python
2 C++
1 C

After Item[String] Property: 

3 Java
4 Python
2 HTML
1 C
5 C#

```

**例 2:**

```cs
// C# code to get or set the value at
// the specified key in StringDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a StringDictionary named my1
        StringDictionary my1 = new StringDictionary();

        // Adding key and value into the StringDictionary
        my1.Add("1", "HTML");
        my1.Add("2", "CSS");
        my1.Add("3", "PHP");
        my1.Add("4", "MongoDB");
        my1.Add("5", "AngularJS");

        // Displaying the keys and
        // values in StringDictionary
        foreach(DictionaryEntry d in my1)
        {
            Console.WriteLine(d.Key + " " + d.Value);
        }

        Console.WriteLine("\nAfter Item[String] Property: \n");

        // setting the value at Key 8
        // here key 8 is not present
        // so it will add a new key/value
        // pair. see output
        my1["8"] = "C#";

        // Displaying the keys and
        // values in StringDictionary
        foreach(DictionaryEntry d1 in my1)
        {
            Console.WriteLine(d1.Key + " " + d1.Value);
        }
    }
}
```

**输出:**

```cs
3 PHP
5 AngularJS
4 MongoDB
2 CSS
1 HTML

After Item[String] Property: 

3 PHP
4 MongoDB
2 CSS
1 HTML
8 C#
5 AngularJS

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string dictionary . item？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringdictionary.item?view=netframework-4.7.2)