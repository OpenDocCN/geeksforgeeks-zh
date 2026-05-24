# C# |等于(字符串，字符串)方法

> 原文:[https://www . geesforgeks . org/c-sharp-equals string-method/](https://www.geeksforgeeks.org/c-sharp-equalsstring-string-method/)

在 C# 中， ***等于(String，String)*** 是一个 String 方法。它用于确定两个字符串对象是否具有相同的值。基本上，它检查平等。如果两个字符串具有相同的值，则返回 true，否则返回 false。此方法不同于比较和比较方法。此方法基于内容比较两个字符串。
**语法:**

```cs
bool string.Equals(string str1, string str2)
```

**说明:**该方法将两个参数以字符串对象的形式取值，检查是否相等。检查后，此方法将返回布尔值。该方法的返回值类型为**系统。布尔**如果 str1 的值与 str2 的值相同，该方法将返回**真**，否则返回**假**。如果 str1 和 str2 都为**空**，则该方法将返回**真**。
**示例:**

```cs
Input:          string str1 = "ProGeek 2.0";
                string str2 = "ProGeek 2.0";
                string.Equals(str1, str2)
Output:         True

Input:          string str3 = "GFG";
                string str4 = "others";
                string.Equals(str3, str4)
Output:         False
```

下面是演示上述方法的程序:

*   **程序 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the Equals() Method
using System;

class GFG {

    // Main Method
    public static void Main(string[] args)
    {
        string s1 = "ProGeek 2.0";
        string s2 = "ProGeek 2.0";

        // Equals() method return true
        // as both string objects are equal
        Console.WriteLine(s1.Equals(s2));
    }
}
```

**Output:** 

```cs
True
```

*   **程序 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the Equals() Method
using System;
class Geeks {

    // Main Method
    public static void Main(string[] args)
    {
        string s1 = "GFG";
        string s2 = "others";

        // this will give result false as
        // both s1 and s2 are different
        Console.WriteLine(s1.Equals(s2));
    }
}
```

**Output:** 

```cs
False
```