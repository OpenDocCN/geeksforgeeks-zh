# 弦。用例子格式化 C# 中的()方法|集合–1

> 原文:[https://www . geesforgeks . org/string-format-method-in-c-sharp-with-examples-set-1/](https://www.geeksforgeeks.org/string-format-method-in-c-sharp-with-examples-set-1/)

在 C# 中， ***格式()*** 是一种 [**串**](https://www.geeksforgeeks.org/c-string/) 的方法。此方法 用于将指定字符串中的一个或多个格式项替换为指定对象的字符串表示。换句话说，这个方法是用来将变量或对象或表达式的值插入到另一个字符串**中。**

这个方法可以通过传递不同类型的参数来重载。格式()方法的重载列表中总共有 **8** 方法，其中 **3** 在本文中讨论，其余在 **Set-2 和 Set-3** 中讨论。

1.  **弦。格式(字符串优先，对象优先)方法**
2.  **弦。格式(字符串，参数对象[])方法**
3.  **弦。格式(表单提供者、字符串、对象)方法**
4.  **弦。格式(表单提供者、字符串、对象、对象)方法**
5.  **弦。格式(表单提供者、字符串、对象、对象、对象)方法**
6.  **弦。格式(表单提供者、字符串、对象[])方法**
7.  **弦。格式(字符串、对象、对象)方法**
8.  **弦。格式(字符串、对象、对象、对象)方法**

## **弦。格式(字符串优先，对象优先)方法**

此方法用于用指定对象的字符串表示替换字符串中的一个或多个格式项。

**语法:**

```cs
public static string Format (string format, object arg0);

```

**参数:**该方法有以下参数:

> **格式:** 此参数为 *所需的复合格式字符串。*
> 
> **arg0:** 该参数是 对象要格式化的。

**返回值:**此方法返回字符串。它是格式的 副本，其中任何 ***格式*** 项都被***arg 0***的字符串表示所替换。

**示例:**

## C#

```cs
// C# program to illustrate the 
// String.Format(String first, 
// Object second) Method

using System;   

public class GFG    
{    
    // Main method 
    public static void Main(string[] args)    
    {   
        DateTime date1 = new DateTime(2019, 11, 11);

        // Converts the object to string
        string s1 = string.Format("{0:D}", date1);  
        Console.WriteLine(s1);  
    }    
}
```

**输出:**

```cs
Monday, 11 November 2019

```

## **弦。格式(字符串，参数对象[])方法**

此方法用于将指定字符串中的格式项替换为指定数组中相应对象的字符串表示形式。

**语法:**

```cs
public static string Format (string format, params object[] args);

```

**参数:**该方法有以下参数:

> **格式:** 此参数为 *所需的复合格式字符串。*
> 
> **参数:**此参数是包含零个或多个要格式化的对象的 对象数组。

**返回值:**此方法返回字符串。它是格式的 副本，其中 ***格式*** 项被***args***的字符串表示所替换。

**示例:**

## C#

```cs
// C# program to illustrate the 
// String.Format(String, 
// params Object[]) Method

using System;   

public class GFG    
{    
    // Main method 
    public static void Main(string[] args)    
    {   
        DateTime date1 = new DateTime(2020, 5, 20);
        TimeSpan hiTime = new TimeSpan(14, 17, 32);
        decimal hiTemp = 24.1m; 
        TimeSpan loTime = new TimeSpan(3, 16, 10);
        decimal loTemp = 21.8m; 

        // Converts the object to string
        string result1 = String.Format("Temperature on {0:d}:\n{1,11}: {2} degrees"+
                                       " (hi)\n{3,11}: {4} degrees (lo)", date1, 
                                                    hiTime, hiTemp, loTime, loTemp);
        Console.WriteLine(result1); 
    }    
}
```

**输出:**

```cs
Temperature on 05/20/2020:
   14:17:32: 24.1 degrees (hi)
   03:16:10: 21.8 degrees (lo)

```

## **弦。格式(表单提供者、字符串、对象)方法**

此方法用于将指定字符串中的一个或多个格式项替换为相应对象的字符串表示形式。参数提供区域性特定的格式信息。

**语法:**

```cs
public static string Format (IFormatProvider provider, string format, object arg0);

```

**参数:**该方法有以下参数:

> **提供程序:**该参数是提供特定于区域性的格式信息的 对象。
> 
> **格式:** 此参数为 *所需的复合格式字符串。*
> 
> **arg0:** 该参数是 对象要格式化的。

**返回值:**此方法返回字符串。它是格式的 副本，其中 ***格式*** 项被***arg 0***的字符串表示所替代。

**示例:**

## C#

```cs
// C# program to illustrate the
// String.Format(IFormatProvider, 
// String, Object) Method

using System;

public class GFG {

// Main method
public static void Main(string[] args) {

    DateTime dateToDisplay = new DateTime(2020, 5, 20, 18, 32, 0);
    System.Globalization.CultureInfo culture =
        new System.Globalization.CultureInfo("en-US");
    string output = String.Format(culture, "{0,-35:D}", dateToDisplay);
    Console.WriteLine(output);
  }
}
```

**输出:**

```cs
Wednesday, May 20, 2020 

```