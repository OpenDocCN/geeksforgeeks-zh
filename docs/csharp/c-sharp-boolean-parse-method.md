# C# |布尔型。解析()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-boolean-parse-method/](https://www.geeksforgeeks.org/c-sharp-boolean-parse-method/)

此方法用于将逻辑值的指定[字符串](https://www.geeksforgeeks.org/c-string/)表示转换为其布尔等价形式。

**语法:**

```cs
public static bool Parse (string value);
```

这里*值*是包含要转换的值的字符串。
**返回值:**如果*值*相当于 TrueString *则此方法返回 *true* 如果值相当于 FalseString 则返回*。
**例外:**

*   **ArgumentNullException:** 如果字符串*值*为空。
*   **格式异常:**如果*值*不等于 TrueString 或 FalseString。

下面的程序说明了**布尔值的使用。解析(字符串)**方法:
**示例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Boolean.Parse(String)
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // passing different values
            // to the method to check
            checkParse("true");
            checkParse("TRUE");
            checkParse("false");
            checkParse("FALSE");
            checkParse(bool.TrueString);
            checkParse(bool.FalseString);
        }

        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (FormatException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining checkParse method
    public static void checkParse(string input)
    {

        // declaring bool variable
        bool val;

        // getting parsed value
        val = bool.Parse(input);
        Console.WriteLine("'{0}' parsed as {1}", input, val);
    }
}
```

**Output:** 

```cs
'true' parsed as True
'TRUE' parsed as True
'false' parsed as False
'FALSE' parsed as False
'True' parsed as True
'False' parsed as False
```