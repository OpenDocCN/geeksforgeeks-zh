# C# | Double。ToString()方法|设置–1

> 原文:[https://www . geesforgeks . org/c-sharp-double-tostring-method-set-1/](https://www.geeksforgeeks.org/c-sharp-double-tostring-method-set-1/)

**翻倍。ToString()方法**用于将当前实例的数值转换为其等价的字符串表示形式。该方法的重载列表中有以下 4 种方法:

*   **串(弦)法**
*   **ToString()方法**
*   **ToString(表单提供者)方法**
*   **字符串(字符串，表单提供者)方法**

在这里，我们将讨论前两种方法。

#### 字符串方法

此方法用于使用指定的格式将当前实例的数值转换为其等效的字符串表示形式。

> **语法:**公共字符串 ToString(字符串格式)；
> 这里，它需要一个数字格式的字符串。
> 
> **返回值:**该方法返回当前实例值的字符串表示形式，由*格式*指定。
> 
> **异常:**如果格式无效，此方法抛出*格式异常*。

**例 1:**

```cs
// C# program to demonstrate the
// Double.ToString(String) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring and initializing value
            double value = 16325.62d;

            // Declaring and initializing format
            string s = "E04";

            // using the method
            string str = value.ToString(s);

            // Display the value
            Console.WriteLine("String value is {0}", str);
        }

        catch (FormatException e) 
        {
            Console.WriteLine("Format is invalid.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
String value is 1.6326E+004

```

**例 2:** 为*格式异常*

```cs
// C# program to demonstrate the
// Double.ToString(String) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring and initializing value
            double value = 16325.62d;

            // Declaring and initializing format
            string s = "a";

            // using the method
            string str = value.ToString(s);

            // Display the value
            Console.WriteLine("String value is {0}", str);
        }

        catch (FormatException e) 
        {
            Console.WriteLine("Format is invalid.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
Format is invalid.
Exception Thrown: System.FormatException

```

#### ToString()方法

此方法用于将当前实例的数值转换为其等效的字符串表示形式。

> **语法:**公共覆盖字符串 ToString()；
> 
> **返回值:**这个方法返回一个代表这个实例值的字符串。

下面的程序说明了 **Double 的使用。**方法:

**例 1:**

```cs
// C# program to demonstrate the
// Double.ToString()  Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring and initializing value
        double value = 7922816251426433759354.39503305d;

        // using ToString() method
        string round = value.ToString();

        // Display the value
        Console.WriteLine("String value is {0}", round);
    }
}
```

**Output:**

```cs
String value is 7.92281625142643E+21

```

**例 2:**

```cs
// C# program to demonstrate the
// Double.ToString() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // calling get() method
        get(20.3495d);
        get(30.5945994d);
        get(40d);
        get(4294967295.5858d);
    }

    // defining get() method
    public static void get(double value)
    {

        // using ToString() method
        string round = value.ToString();

        // Display the value
        Console.WriteLine("String value is {0}", round);
    }
}
```

**Output:**

```cs
String value is 20.3495
String value is 30.5945994
String value is 40
String value is 4294967295.5858

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . double . tostring？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.double.tostring?view=netframework-4.7.2)