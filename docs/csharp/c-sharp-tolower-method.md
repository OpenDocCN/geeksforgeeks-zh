# C# | ToLower()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-tolower-method/](https://www.geeksforgeeks.org/c-sharp-tolower-method/)

在[c# ](https://www.geeksforgeeks.org/introduction-to-c-sharp/)**T3【to lower()T5【是一个串法。它会将每个字符转换为小写(如果有小写字符)。如果一个字符没有对应的小写字母，它将保持不变。例如，特殊符号保持不变。可以通过向该方法传递不同类型的参数来重载该方法。**

*   **字符串。ToLower()方法***   **String.ToLower(CultureInfo) Method

    #### 字符串。ToLower()方法

    此方法用于返回转换为小写的当前字符串的副本。

    **语法:**

    ```cs
    public string ToLower ();

    ```

    **返回类型:**它返回字符串值，该值是类型为*系统的字符串的小写等价物。弦*。

    **示例:**

    ```cs
    Input : str  = "GeeksForGeeks"
            str.ToLower()
    Output: geeksforgeeks

    Input : str  = "This is C# Program xsdD_$#%"
            str.ToLower()
    Output: this is c# program xsdd_$#%

    ```

    以下程序说明了 ToLower()方法的使用:

    *   **Example 1:**

        ```cs
        // C# program to desmonstrate the 
        // use of ToLower() method 
        using System;

        class Program {

            // Main Method
            public static void Main()
            {

                // original string
                string str1 = "GeeksForGeeks";

                // string converted to lower case
                string lowerstr1 = str1.ToLower();

                Console.WriteLine(lowerstr1);
            }
        }
        ```

        **输出:**

        ```cs
        geeksforgeeks

        ```

    *   **Example 2:**

        ```cs
        // C# program to desmonstrate the 
        // use of ToLower() method 
        using System;

        class Program {

            // Main Method
            public static void Main()
            {

                // original string containing the special
                // symbol. Here special symbol will remain 
                // unchange
                string str2 = "This is C# Program xsdD_$#%";

                // string converted to lower case
                string lowerstr2 = str2.ToLower();

                Console.WriteLine(lowerstr2);
            }
        }
        ```

        **输出:**

        ```cs
        this is c# program xsdd_$#%

        ```** 

#### **字符串。ToLower(CultureInfo)方法**

**此方法用于使用指定区域性的大小写规则返回转换为小写的当前字符串的副本。**

****语法:****

```cs
public string ToLower (System.Globalization.CultureInfo culture); 
```

****参数:****

> ****文化:**是提供特定文化外壳规则的必需对象。**

****返回类型:**该方法返回类型为*系统的当前字符串的小写等价物。弦*。**

****异常:**如果*文化*的值为空，这个方法可以给出 *ArgumentNullException* 。**

****示例:****

```cs
// C# program to desmonstrate the 
// use of ToLower(CultureInfo) method 
using System;
using System.Globalization;

class Program {

    // Main Method
    public static void Main()
    {
        // original string
        string str2 = "THIS IS C# PROGRAM XSDD_$#%";

        // string converted to lowercase by
        // using English-United States culture
        string lowerstr2 = str2.ToLower(new CultureInfo("en-US", false));

        Console.WriteLine(lowerstr2);
    }
}
```

****输出:****

```cs
this is c# program xsdd_$#% 
```

****注意:**这些方法不会修改当前实例的值。而是返回一个新字符串，其中当前实例中的所有字符都将转换为小写。**

****参考:**T2？视图=netframework-4.7.2**