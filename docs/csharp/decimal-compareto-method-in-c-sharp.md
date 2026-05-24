# 小数。C# 中的 CompareTo()方法

> 原文:[https://www . geesforgeks . org/decimal-compare to-method-in-c-sharp/](https://www.geeksforgeeks.org/decimal-compareto-method-in-c-sharp/)

此方法用于将当前实例与指定的对象或小数进行比较，并返回其相对值的指示。该方法的重载列表中有 2 种方法如下:

*   **Comparison (decimal) method**
*   **Comparison (object) method**

#### 小数。比较法

此方法用于将当前实例与指定的 Decimal 对象进行比较，并返回它们的相对值的比较结果。

**语法:**

```cs
public int CompareTo (decimal value);
```

这里，它将对象与这个实例进行比较。

**返回值:**返回一个 32 位有符号数，表示当前实例和*值*参数的相对值，如下所示:

*   **小于零:**如果当前实例<值
*   **如果当前实例=值，则为零:**
*   **大于零:**如果当前实例>值

下面的程序说明了*小数的使用。比较(十进制)*方法

**例 1:**

## c#

```cs
// C# program to demonstrate the
// Decimal.CompareTo(Double) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring and initializing value1
        decimal value1 = 10;

        // Declaring and initializing value2
        decimal value2 = 20;

        // compare both decimal value
        // using CompareTo() method
        int status = value1.CompareTo(value2);

        // checking the status
        if (status > 0)
            Console.WriteLine("{0} is greater than {1}",
                                        value1, value2);
        else if (status < 0)
            Console.WriteLine("{0} is less than {1}",
                                     value1, value2);
        else
            Console.WriteLine("{0} is equal to {1}",
                                    value1, value2);
    }
}
```

**输出:**

```cs
10 is less than 20
```

**例 2:**

## c#

```cs
// C# program to demonstrate the
// Decimal.CompareTo(Double) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        get(5, 7);
        get(30, 20);
        get(10, 20);
        get(7, -12);
    }

    // defining get() method
    public static void get(decimal value1,
                          decimal value2)
    {

        // using CompareTo() method
        int status = value1.CompareTo(value2);

        // checking the status
        if (status > 0)
            Console.WriteLine("{0} is greater than {1}",
                                        value1, value2);
        else if (status < 0)
            Console.WriteLine("{0} is less than {1}",
                                     value1, value2);
        else
            Console.WriteLine("{0} is equal to {1}",
                                    value1, value2);
    }
}
```

**输出:**

```cs
5 is less than 7
30 is greater than 20
10 is less than 20
7 is greater than -12
```

#### 小数。比较对象方法

此方法用于将当前实例与指定对象进行比较，并返回它们相对值的比较结果。

**语法:**

```cs
public int CompareTo (object value);
```

这里，它将对象与这个实例进行比较，或者为 null。

**返回值:**返回一个 32 位有符号数，表示当前实例与*值*参数的相对值，如下所示:

*   **is less than zero:** If the current instance < value
*   **Zero:** If the current instance = value
*   **is greater than zero:** If the current instance > value

**异常:**如果值不为空，则抛出*参数异常*。

下面的程序说明了*小数的使用。比较(对象)*方法

**例 1:**

## c#

```cs
// C# program to demonstrate the
// Decimal.CompareTo(object) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring and initializing value1
            decimal value1 = 10;

            // Declaring and initializing value2
            object value2 = (decimal)9.8765400E+2;

            // compare both decimal value
            // using CompareTo() method
            int status = value1.CompareTo(value2);

            // checking the status
            if (status > 0)
                Console.WriteLine("{0} is greater than {1}",
                                            value1, value2);

            else if (status < 0)
                Console.WriteLine("{0} is less than {1}",
                                       value1, value2);
            else
                Console.WriteLine("{0} is equal to {1}",
                                        value1, value2);
        }

        catch (ArgumentException e)
        {
            Console.WriteLine("value2 must be decimal");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出:**

```cs
10 is less than 987.654
```

**例 2:** 为*ArgumentException*

## c#

```cs
// C# program to demonstrate the
// Decimal.CompareTo(object) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring and initializing value1
            decimal value1 = 10;

            // Declaring and initializing value2
            object value2 = 1 / 3;

            // using CompareTo() method
            int status = value1.CompareTo(value2);

            // checking the status
            if (status > 0)
                Console.WriteLine("{0} is greater than {1}",
                                            value1, value2);

            else if (status < 0)
                Console.WriteLine("{0} is less than {1}",
                                         value1, value2);
            else
                Console.WriteLine("{0} is equal to {1}",
                                        value1, value2);
        }

        catch (ArgumentException e)
        {
            Console.WriteLine("value2 must be decimal");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出:**

```cs
value2 must be decimal
Exception Thrown: System.ArgumentException
```

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。十进制。相比于？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.compareto?view=netframework-4.7.2)