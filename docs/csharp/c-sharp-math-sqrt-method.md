# C# |数学。Sqrt()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-math-sqrt-method/](https://www.geeksforgeeks.org/c-sharp-math-sqrt-method/)

在 C# 中 ***数学。*sqrt()**是一种数学类方法，用于计算指定数字的平方根。
Sqrt 是一种较慢的计算。可以缓存它以提高性能。
**语法:**

```cs
public static double Sqrt(double d)

```

**参数:**

> d:要计算平方根的数字，该参数类型为*系统。双*。

**返回类型:**该方法返回 d 的平方根，如果 d 等于 NaN、NegativeInfinity 或 PositiveInfinity，则返回该值。这种方法的返回类型是*系统。双*。

**示例:**

```cs
Input  : Math.Sqrt(81) 
Output : 9

Input  : Math.Sqrt(-81) 
Output : NaN

Input  : Math.Sqrt(0.09) 
Output : 0.3

Input  : Math.Sqrt(0)
Output : 0

Input  : Math.Sqrt(-0)
Output : 0

```

下面 C# 程序说明了数学的工作原理。Sqrt():

*   **程序 1:** 当参数为正双精度值时，该方法返回给定值的平方根。

    ```cs
    // C# program to illustrate the
    // Math.Sqrt() method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            double x = 81;

            // Input positive value, Output square root of x
            Console.Write(Math.Sqrt(x));
        }
    }
    ```

    **输出:**

    ```cs
    9

    ```

*   **程序 2:** 当参数为负时，此方法将返回 NaN。

    ```cs
    // C# program to illustrate the Math.Sqrt() 
    // method when the argument is Negative
    using System;

    class GFG {

        // Main method
        public static void Main()
        {
            double x = -81;

            // Input Negative value, Output square root of x
            Console.Write(Math.Sqrt(x));
        }
    }
    ```

    **输出:**

    ```cs
    NaN

    ```

*   **程序 3:** 当参数是带小数位的双精度值时，那么这个方法将返回给定值的平方根。

    ```cs
    // C# program to illustrate the Math.Sqrt() 
    // method when the argument is double value
    // with decimal places
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            double x = 0.09;

            // Input value with decimal places, 
            // Output square root of x
            Console.Write(Math.Sqrt(x));
        }
    }
    ```

    **输出:**

    ```cs
    0.3

    ```

*   **程序 4:** 当自变量为正或负的 Zero 时，则返回结果为 Zero。

    ```cs
    // C# program to illustrate the Math.Sqrt() 
    // method when the argument is positive 
    // or negative Zero
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            double x = 0;

            // Input value positive Zero, Output
            // square root of x
            Console.WriteLine(Math.Sqrt(x));
            double y = -0;

            // Input value Negative Zero,
            // Output square root of y
            Console.Write(Math.Sqrt(y));
        }
    }
    ```

    **输出:**

    ```cs
    0
    0

    ```

**注意:**如果值太大，那么其给出的编译时间误差为误差 *CS1021:积分常数太大*。

**参考:**T2】https://msdn.microsoft.com/en-us/library/system.math.sqrt