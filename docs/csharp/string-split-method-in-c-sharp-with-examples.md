# 弦。C# 中的 Split()方法，示例

> 原文:[https://www . geesforgeks . org/string-split-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/string-split-method-in-c-sharp-with-examples/)

在 C# 中，Split()是一个[字符串类](https://www.geeksforgeeks.org/c-sharp-string-class/)方法。Split()方法返回一个字符串数组，该数组是通过拆分原始字符串生成的，原始字符串由 Split()方法中作为参数传递的分隔符分隔。分隔符可以是字符或字符数组或字符串数组。也可以说它返回一个字符串数组，该数组包含当前实例中由指定字符串或 Unicode 字符数组的元素分隔的子字符串。
该方法过载列表中有 **6 种方法**如下:

| 方法 | 描述 |
| **分割(字符串[]，Int32，字符串分割)** | 根据作为参数传递的字符串数组，将字符串拆分为最大数量的子字符串。您可以指定是否在子字符串数组中包含空数组元素。 |
| **拆分(Char[]，Int32，stringsplittoptions)** | 根据作为参数传递的字符数组，将字符串拆分为最大数量的子字符串。您可以指定是否在子字符串数组中包含空数组元素。 |
| **Split(String[]，string splitting options)** | 基于字符串数组将字符串拆分为子字符串。您可以指定是否在子字符串数组中包含空数组元素。 |
| **分裂(Char[])** | 基于字符数组将字符串拆分为子字符串。 |
| **Split(Char[]，string splitting options)** | 基于字符数组将字符串拆分为子字符串。您可以指定是否在子字符串数组中包含空数组元素。 |
| **分裂(Char[]，Int32)** | 根据作为参数传递的字符数组，将字符串拆分为最大数量的子字符串。您可以指定要返回的子字符串的最大数量。 |

### 1.拆分(字符串[]，Int32，StringSplitOptions)方法

此方法用于根据数组中的字符串将字符串拆分为最大数量的子字符串。您可以指定子字符串是否包含空数组元素。

**语法:**

```cs
public String[] Split(String[] separator, int count, StringSplitOptions options);

```

**参数:**

*   **分隔符:**它是一个字符串数组，用于分隔该字符串中的子字符串，是一个不包含分隔符的空数组，或者是 null。
*   **计数:**是返回的最大子串数。
*   **选项:** *删除空数组元素*选项从返回的数组中省略空数组元素，或者选择无选项在返回的数组中包含空数组元素。

**Return:** 该方法返回一个数组，该数组的元素包含该字符串中由分隔符中的一个或多个字符分隔的子字符串。

**异常:**

*   **argumentoutofrangerexception:**如果*计数*为负。
*   **参数异常:**如果*选项*不是字符串选项之一。

**示例:**

```cs
// C# program to illustrate the 
// Split(String[], Int32, StringSplitOptions)
// Method
using System;

class GFG {

    // Main Method    
    static void Main(string[] args)
    {

        // Taking a string
        String str = "Geeks, For Geeks";

        String[] spearator = { "s, ", "For" };
        Int32 count = 2;

        // using the method
        String[] strlist = str.Split(spearator, count,
               StringSplitOptions.RemoveEmptyEntries);

        foreach(String s in strlist)
        {
            Console.WriteLine(s);
        }
    }
}
```

**输出:**

```cs
Geek
 Geeks

```

### 2.拆分(Char[]，Int32，StringSplitOptions)方法

此方法用于根据数组中的字符将字符串拆分为最大数量的子字符串。

**语法:**

```cs
public String[] Split(char[] separator, int count, StringSplitOptions options);

```

**参数:**

*   **分隔符:**是分隔该字符串中子字符串的字符数组、不包含分隔符的空数组或 null。
*   **计数:**是返回的最大子串数。
*   **选项:** RemoveEmptyEntries 选项从返回的数组中省略空数组元素，或者 None 选项在返回的数组中包含空数组元素。

**Return:** 它是一个数组，其元素包含该字符串中由分隔符中的一个或多个字符分隔的子字符串。

**异常:**

*   **argumentoutofrangerexception:**如果计数为负。
*   **参数异常:**如果选项不是 StringSplitOptions 值之一。

**示例:**

```cs
// C# program to illustrate the
// Split(Char[], Int32, 
// StringSplitOptions) Method
using System;

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Taking a string
        String str = "Geeks, For Geeks";

        char[] spearator = { ',', ' ' };
        Int32 count = 2;

        // Using the Method
        String[] strlist = str.Split(spearator, 
               count, StringSplitOptions.None);

        foreach(String s in strlist)
        {
            Console.WriteLine(s);
        }
    }
}
```

**输出:**

```cs
Geeks
 For Geeks

```

### 3.分割(字符串[]，字符串分割)方法

此方法用于根据数组中的字符串将字符串拆分为子字符串。您可以指定子字符串是否包含空数组元素。

**语法:**

```cs
public String[] Split(String[] separator, StringSplitOptions options);

```

**参数:**

*   **分隔符:**它是一个字符串数组，用于分隔该字符串中的子字符串，是一个不包含分隔符的空数组，或者是 null。
*   **选项:** RemoveEmptyEntries 选项从返回的数组中省略空数组元素，或者 None 选项在返回的数组中包含空数组元素。

**返回:**该方法返回一个字符串数组，该数组的元素包含该字符串中由分隔符中的一个或多个字符分隔的子字符串。

**异常:**如果*选项*参数不是 StringSplitOptions 值之一，此方法将给出*参数异常*。

**示例:**

```cs
// C# program to illustrate the 
// Split(String[], StringSplitOptions) 
// Method
using System;

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Taking a string
        String str = "Geeks, For Geeks";

        String[] spearator = { "s,", "For" };

        // using the method
        String[] strlist = str.Split(spearator, 
           StringSplitOptions.RemoveEmptyEntries);

        foreach(String s in strlist)
        {
            Console.WriteLine(s);
        }
    }
}
```

**输出:**

```cs
Geek

 Geeks

```

### 4.拆分(char[])方法

此方法用于将字符串拆分为基于数组中字符的子字符串。

**语法:**

```cs
public String[] Split(char[] separator);

```

这里，*分隔符*是一个字符数组，用于分隔该字符串中的子字符串，是一个不包含分隔符的空数组，或者是 null。

**返回:**返回一个字符串数组，其元素包含该字符串中由分隔符中的一个或多个字符分隔的子字符串。

**示例:**

```cs
// C# program to illustrate the 
// Split(char[]) Method
using System;

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Taking a string
        String str = "Geeks, For Geeks";

        char[] spearator = { ',', ' ' };

        // using the method
        String[] strlist = str.Split(spearator);

        foreach(String s in strlist)
        {
            Console.WriteLine(s);
        }
        Console.ReadKey();
    }
}
```

**输出:**

```cs
Geeks

For
Geeks

```

### 5.拆分(char[]，StringSplitOptions)方法

此方法用于根据数组中的字符将字符串拆分为子字符串。您可以指定子字符串是否包含空数组元素。

**语法:**

```cs
public String[] Split(char[] separator, StringSplitOptions option);

```

**参数:**

*   **分隔符:**是分隔该字符串中子字符串的字符数组、不包含分隔符的空数组或 null。
*   **选项:** RemoveEmptyEntries 选项从返回的数组中省略空数组元素，或者 None 选项在返回的数组中包含空数组元素。

**返回:**该方法返回一个数组，该数组的元素包含该字符串中由*分隔符*中的一个或多个字符分隔的子字符串。

**示例:**

```cs
// C# program to illustrate the use of
// Split(Char[], StringSplitOptions) method
using System;

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Taking a string
        String str = "Geeks, For Geeks";

        char[] spearator = { ',', ' ' };

        // using the method
        String[] strlist = str.Split(spearator, 
           StringSplitOptions.RemoveEmptyEntries);

        foreach(String s in strlist)
        {
            Console.WriteLine(s);
        }
    }
}
```

**输出:**

```cs
Geeks
For
Geeks

```

### 6.拆分(char[]，Int32)方法

此方法用于根据数组中的字符将字符串拆分为最大数量的子字符串。您还可以指定要返回的子字符串的最大数量。

**语法:**

```cs
public String[] Split(char[] separator, Int32 count);

```

**参数:**

*   **分隔符:**分隔该字符串中的子字符串的字符数组、不包含分隔符的空数组或 null。
*   **计数:**是返回的最大子串数。

**返回:**该方法返回一个数组，该数组的元素包含由*分隔符*中的一个或多个字符分隔的子字符串。

**异常:**如果计数为负，此方法将给出*argumentout of range Exception*。

**示例:**

```cs
// C# program to illustrate the use of
// Split(char[], Int32) Method
using System;

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Taking a string
        String str = "Geeks, For Geeks";

        char[] spearator = { ',', ' ' };
        Int32 count = 2;

        // using the method
        String[] strlist = str.Split(spearator, count);

        foreach(String s in strlist)
        {
            Console.WriteLine(s);
        }

    }
}
```

**输出:**

```cs
Geeks
 For Geeks

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . string . split？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.string.split?view=netframework-4.8)