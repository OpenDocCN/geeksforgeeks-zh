# C# |字符串。标准化方法

> 原文:[https://www . geesforgeks . org/c-sharp-string-is normalized-method/](https://www.geeksforgeeks.org/c-sharp-string-isnormalized-method/)

**IsNormalized()方法**用于检查给定的字符串是否为特定的 Unicode 规范化形式。如果给定的字符串是特定的规范化形式，则此方法返回 true。否则，返回 false。
该方法过载列表中有**两种**方法如下:

1.  **是正式化的()**
2.  **被规范化(规范化形式)**

**要点:**

*   一些 Unicode 字符有多个等价的二进制表示，这使得搜索、排序、匹配和其他操作变得复杂。
*   Unicode 标准定义了一个称为**规范化**的过程，当给定一个字符的任何等价二进制表示时，该过程返回一个二进制表示。规范化可以用几个算法来执行，这些算法被称为规范化形式，它们遵循不同的规则。
*   。NET 目前支持规范化形式 C、D、KC 和 KD。

#### IsNormalized()

此方法用于检查给定的字符串是否为 Unicode 规范化形式 C。如果字符串是 Unicode 规范化形式，则此方法返回 true，否则返回 false。
**语法:**

```cs
public bool IsNormalized ();
```

**返回值:**该方法的返回类型为**系统。布尔**。当给定字符串为规范化形式 C 时，该方法返回 true 当给定字符串不为规范化形式 C 时，该方法返回 false，即
**异常:**如果当前实例包含无效的 Unicode 字符，则该方法将给出 **ArgumentException** 。
**例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// IsNormalized() method
using System;
using System.Text;

class GFG {

    // Main method
    static public void Main()
    {

        // string
        string str1 = "Hello, Geeks!";

        bool value;

        // check the given string is
        // in normalized form or not
        // using IsNormalized() method
        value = str1.IsNormalized();

        // Display the data
        Console.WriteLine("String is : {0}", str1);
        Console.WriteLine("Is str1 string is in normalized form?: {0}",
                                                                value);
    }
}
```

**Output:** 

```cs
String is : Hello, Geeks!
Is str1 string is in normalized form?: True
```

**注意:**IsNormalized 方法返回 false，因为它会遇到字符串中的第一个非规范化字符。因此，如果一个字符串包含非规范化字符后跟无效的 Unicode 字符，规范化方法将抛出一个*参数异常*，尽管 IsNormalized 返回 *false* 。

#### 标准化(标准化形式)

此方法用于检查给定字符串是否采用指定的 Unicode 规范化形式。如果给定的字符串是指定的 Unicode 规范化形式，则此方法将返回 true，否则返回 false。
**语法:**

```cs
public bool IsNormalized (NormalizationForm nform);
```

这里，*nfrm*是一个 Unicode 规范化形式。
**返回值:**该方法的返回类型为**系统。布尔**。如果该字符串是由*n for*参数指定的规范化形式，则该方法返回 **true** 。否则，返回**假**。
**异常:**如果当前实例包含无效的 Unicode 字符，此方法将给出 **ArgumentException** 。
**例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// IsNormalized(NormalizationForm) method
using System;
using System.Text;

class Sample {

    // Main method
    public static void Main()
    {

        // create and initialize string
        string str1 = "GeeksforGeeks!";

        // Display and check the given string
        // is in C, D, KC, and KD normalized form
        // Using IsNormalized(NormalizationForm) method
        Console.WriteLine("Is string str1 is normalized to form C - {0}",
                             str1.IsNormalized(NormalizationForm.FormC));

        Console.WriteLine("Is string str1 is normalized to form D - {0}",
                             str1.IsNormalized(NormalizationForm.FormD));

        Console.WriteLine("Is string str1 is normalized to form KC - {0}",
                             str1.IsNormalized(NormalizationForm.FormKC));

        Console.WriteLine("Is string str1 is normalized to form KD - {0}",
                             str1.IsNormalized(NormalizationForm.FormKD));
    }
}
```

**Output:** 

```cs
Is string str1 is normalized to form C - True
Is string str1 is normalized to form D - True
Is string str1 is normalized to form KC - True
Is string str1 is normalized to form KD - True
```

**参考:**[https://docs . Microsoft . com/en-us/dotnet/API/system . string . is normalized？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.string.isnormalized?view=netframework-4.7.2)