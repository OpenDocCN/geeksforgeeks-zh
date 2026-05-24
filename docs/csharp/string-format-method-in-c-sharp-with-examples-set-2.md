# 弦。用例子格式化 C# 中的()方法|集合–2

> 原文:[https://www . geesforgeks . org/string-format-method-in-c-sharp-with-examples-set-2/](https://www.geeksforgeeks.org/string-format-method-in-c-sharp-with-examples-set-2/)

在 C# 中， ***格式()*** 是一种 [**串**](https://www.geeksforgeeks.org/c-string/) 的方法。此方法 用于将指定字符串中的一个或多个格式项替换为指定对象的字符串表示。换句话说，这个方法是用来将变量或对象或表达式的值插入到另一个字符串**中。**

这个方法可以通过传递不同类型的参数来重载。格式()方法的过载列表中总共有 **8** 种方法，其中 **3** 在 **Set-1** 中讨论，其余的在 **Set-2 和 Set-3** 中讨论。

1.  **弦。格式(字符串优先，对象优先)方法**
2.  **弦。格式(字符串，参数对象[])方法**
3.  **弦。格式(表单提供者、字符串、对象)方法**
4.  **弦。格式(表单提供者、字符串、对象[])方法**
5.  **弦。格式(字符串、对象、对象)方法**
6.  **弦。格式(字符串、对象、对象、对象)方法**
7.  **弦。格式(表单提供者、字符串、对象、对象)方法**
8.  **弦。格式(表单提供者、字符串、对象、对象、对象)方法**

## **弦。格式(表单提供者、字符串、对象[])方法**

此方法用于将字符串中的格式项替换为指定数组中相应对象的字符串表示。参数提供区域性特定的格式信息。

**语法:**

```cs
public static string Format (IFormatProvider provider, string format, params object[] args);

```

**参数:**该方法有以下参数:

> **提供程序:**该参数是提供特定于区域性的格式信息的 对象。
> 
> **格式:** 此参数为 *所需的复合格式字符串。*
> 
> **参数:**此参数是包含零个或多个要格式化的对象的 对象数组。

**返回值:**此方法返回字符串。它是格式的 副本，其中 ***格式*** 项被 ***参数*** 中相应对象的字符串表示所替代。

**示例:**

## C#

```cs
// C# program to illustrate the 
// String.Format(IFormatProvider,
// String,Object[]) Method

using System;   

public class GFG    
{    
    // Main method 
    public static void Main(string[] args)    
    {   

        DateTime dateToDisplay = 
        new DateTime(2020, 5, 20, 18, 32, 0);

        System.Globalization.CultureInfo 
        culture = new System.Globalization.
        CultureInfo("en-US");

        string output = String.Format
        (culture, "{0,-11} {1,-35:D}",
         culture.Name, dateToDisplay);

        Console.WriteLine(output);
    }    
}
```

**输出:**

```cs
en-US       Wednesday, May 20, 2020

```

## **弦。格式(字符串、对象、对象)方法**

此方法用于将字符串中的格式项替换为两个指定对象的字符串表示形式。

**语法:**

```cs
public static string Format (string format, object arg0, object arg1);

```

**参数:**该方法有以下参数:

> **格式:** 此参数为 *所需的复合格式字符串。*
> 
> **arg0:** 该参数是 第一个要格式化的对象。
> 
> **arg1:** 该参数是 第二个要格式化的对象。

**返回值:**此方法返回字符串。它是格式的 副本，其中 ***格式*** 项被**arg 0****和** ****arg1** 的字符串表示所取代。**

****示例:****

## **C#**

```cs
// C# program to illustrate the 
// String.Format(String, Object,
// Object) Method

using System;   

public class GFG    
{    
    // Main method 
    public static void Main(string[] args)    
    {   

        string formatString = 
        "Value: {0,0}\n" + 
        "NOT of Value: {1,0}";

        int value1 = 169;

        string result = String.Format
        (formatString, value1, ~value1);

        Console.WriteLine(result);
    }    
}
```

****输出:****

```cs
Value: 169
NOT of Value: -170 
```

## ****弦。格式(字符串、对象、对象、对象)方法****

**此方法用于将字符串中的格式项替换为三个指定对象的字符串表示形式。**

****语法:****

```cs
public static string Format (string format, object arg0, object arg1, object arg2); 
```

****参数:**该方法有以下参数:**

> ****格式:** 此参数为 *所需的复合格式字符串。***
> 
> ****arg0:** 该参数是 第一个要格式化的对象。**
> 
> ****arg1:** 该参数是 第二个要格式化的对象。**
> 
> ****arg2:** 该参数是 第三个要格式化的对象。**

****返回值:**此方法返回字符串。它是格式的 副本，其中 ***格式*** 项被 **arg0** **、** **arg1 和 arg2** 的字符串表示所取代。**

****示例:****

## **C#**

```cs
// C# program to illustrate the 
// String.Format(String, Object,
// Object, Object) Method

using System;   

public class GFG    
{    
    // Main method 
    public static void Main(string[] args)    
    {   

        string formatString = 
        "Value 1: {0,0}\n" + 
        "Value 2: {1,0}\n"+
        "Sum of Values : {2,0}";

        int value1 = 169;
        int value2 = 961;

        string result = String.Format
        (formatString, value1, value2, 
        value1 + value2);

        Console.WriteLine(result);
    }    
}
```

****输出:****

```cs
Value 1: 169
Value 2: 961
Sum of Values : 1130 
```