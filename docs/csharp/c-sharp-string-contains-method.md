# C# |字符串。包含()方法

> 原文:[https://www . geesforgeks . org/c-sharp-string-contains-method/](https://www.geeksforgeeks.org/c-sharp-string-contains-method/)

在 C# 中， ***字符串。*包含()**是一个字符串方法。此方法用于检查子字符串是否出现在给定的字符串中。

**语法:**

```cs
public bool Contains(string str)
```

**参数:**

> **str:** 是要检查的字符串。该参数类型为**系统。弦**。

**返回值:**返回布尔值。如果字符串中存在子字符串，或者值为空字符串("")，则返回真，否则返回假。

**异常:**如果*字符串*为*空*，此方法可以给出*参数异常*。

**注意:**此方法执行**区分大小写检查**。搜索将始终从字符串的第一个字符位置开始，一直持续到最后一个字符位置。

下面是说明 Contains()方法的程序。

**程序 1:**

```cs
// C# program to demonstrate the
// String.Contains() Method
using System;

class Geeks {

    // Main Method
    public static void Main()
    {

        // string type
        String str = "GeeksforGeeks";
        String substr1 = "for";
        String substr2 = "For";

        // using String.Contains() Method
        Console.WriteLine(str.Contains(substr1));

        // Here case-sensitive comparison
        // And substr2 value is 'For'
        // So its return false
        Console.WriteLine(str.Contains(substr2));
    }
}
```

**输出:**

```cs
True
False

```

**程序 2:** 使用序数比较和不区分大小写的序数比较来确定字符串中是否存在子字符串。

```cs
// C# program to illustrate the
// String.Contains() Method using
// ordinal comparison and case-
// insensitive ordinal comparison
using System;

public static class StringExtensions {

    // defines a String extension method
    // which includes a StringComparison parameter
    public static bool Contains(this String str,
                                String substr,
                                StringComparison cmp)
    {
        if (substr == null)
            throw new ArgumentNullException("substring substring",
                                            " cannot be null.");

        else if (!Enum.IsDefined(typeof(StringComparison), cmp))
            throw new ArgumentException("comp is not a member of",
                                        "StringComparison, comp");

        return str.IndexOf(substr, cmp) >= 0;
    }
}

// Driver Class
class Geeks {

    // Main Method
    public static void Main()
    {
        String str = "GeeksforGeeks";
        String substr = "FOR";

        // For Ordinal
        StringComparison comp = StringComparison.Ordinal;
        Console.WriteLine("For {0:G}: {1}", comp,
                          str.Contains(substr, comp));

        // for OrdinalIgnoreCase
        comp = StringComparison.OrdinalIgnoreCase;
        Console.WriteLine("For {0:G}: {1}", comp,
                          str.Contains(substr, comp));
    }
}
```

**输出:**

```cs
For Ordinal: False
For OrdinalIgnoreCase: True

```

**程序 3:** 以下示例确定字符串“Computer”是否是给定字符串的子字符串。如果在字符串中找到它，它也会显示它的起始位置。

```cs
// C# program to demonstrate the
// String.Contains() Method
// along with the starting position
using System;

class Example {
    public static void Main()
    {
        string sub1 = "GeeksforGeeks is a Computer Science Portal";
        string sub2 = "Computer";

        // Check if the substring is
        // present in the main string
        bool b = sub1.Contains(sub2);

        Console.WriteLine("'{0}' is in the string '{1}': {2}",
                          sub2, sub1, b);
        if (b) {
            int index = sub1.IndexOf(sub2);
            if (index >= 0)
                Console.WriteLine("{0} begins at character position {1}",
                                  sub2, index + 1);
        }
    }
}
```

**输出:**

```cs
'Computer' is in the string 'GeeksforGeeks is a Computer Science Portal': True
Computer begins at character position 20

```

**参考:**[https://msdn . Microsoft . com/en-us/library/system . string . contains](https://msdn.microsoft.com/en-us/library/dy85x1sa(v=vs.110).aspx)