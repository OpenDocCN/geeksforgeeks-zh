# C# | ToUpper()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-toupper-method/](https://www.geeksforgeeks.org/c-sharp-toupper-method/)

在 **[中 c# ](https://www.geeksforgeeks.org/introduction-to-c-sharp/)*****ToUpper()***是一个串法。它将每个字符都转换成大写(如果有大写版本的话)。如果一个字符没有等同的大写字母，它将保持不变。例如，特殊符号保持不变。这个方法可以通过传递不同类型的参数来重载。

*   **字符串。ToUpper()方法***   **String.ToUpper(CultureInfo) Method

    #### 字符串。ToUpper()方法

    此方法用于返回转换为大写的当前字符串的副本。

    **语法:**

    ```cs
    public string ToUpper();

    ```

    **返回类型:**它的返回字符串值，它是给定字符串的大写等价物。这种方法的返回类型是*系统。弦*。

    **示例:**

    ```cs
    Input : str  = "GeeksForGeeks"
            str.ToUpper()
    Output: GEEKSFORGEEKS

    Input : str  = "This is C# Program xsdd_$#%"
            str.ToUpper()
    Output: THIS IS C# PROGRAM XSDD_$#%

    ```

    **以下示例程序说明了 ToUpper()方法**

    *   **Example 1:**

        ```cs
        // C# program to desmonstrate the 
        // use of ToUpper() method 
        using System;

        class Program {

            // Main Method
            public static void Main()
            {

                // original string
                string str1 = "GeeksForGeeks";

                // string converted to Upper case
                string upperstr1 = str1.ToUpper();

                Console.WriteLine(upperstr1);
            }
        }
        ```

        **输出:**

        ```cs
        GEEKSFORGEEKS

        ```

    *   **Example 2:**

        ```cs
        // C# program to desmonstrate the 
        // use of ToUpper() method 
        using System;

        class Program {

            // Main Method
            public static void Main()
            {
                // original string
                string str2 = "This is C# Program xsdd_$#%";

                // string converted to Upper case
                string upperstr2 = str2.ToUpper();

                Console.WriteLine(upperstr2);
            }
        }
        ```

        **输出:**

        ```cs
        THIS IS C# PROGRAM XSDD_$#%

        ```** 

#### **字符串。方法**

**此方法用于使用指定区域性的大小写规则返回转换为大写的当前字符串的副本。**

****语法:****

```cs
public string ToUpper (System.Globalization.CultureInfo culture); 
```

****参数:****

> ****文化:**是提供特定文化外壳规则的必需对象。**

****返回类型:**该方法返回类型为*系统的当前字符串的大写等价物。弦*。**

****异常:**如果*文化*的值为空，这个方法可以给出 *ArgumentNullException* 。**

****示例:****

```cs
// C# program to desmonstrate the 
// use of ToUpper(CultureInfo) method 
using System;
using System.Globalization;

class Program {

    // Main Method
    public static void Main()
    {
        // original string
        string str2 = "This is C# Program xsdd_$#%";

        // string converted to Uppercase by
        // using English-United States culture
        string upperstr2 = str2.ToUpper(new CultureInfo("en-US", false));

        Console.WriteLine(upperstr2);
    }
}
```

****输出:****

```cs
THIS IS C# PROGRAM XSDD_$#% 
```

****注意:**这些方法不会修改当前实例的值。相反，它们返回一个新字符串，其中当前实例中的所有字符都将转换为大写。**

****参考:**T2？视图=netframework-4.7.2**