# 翻倍。C# 中的方法与示例的比较

> 原文:[https://www . geeksforgeeks . org/double-compare to-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/double-compareto-method-in-c-sharp-with-examples/)

**翻倍。比较方法**用于将当前实例与指定对象或*双*对象进行比较。它将返回一个整数，显示当前实例的值是大于、小于还是等于指定对象的值还是*双*对象的值。此方法的重载列表中有 2 种方法，如下所示:

*   **比较(双)法***   **CompareTo(Object) Method

    #### 双倍。比较(双)法

    **翻倍。CompareTo()** 方法用于将当前实例与指定的双精度浮点数进行比较，并返回一个整数，该整数显示此实例的值是小于、等于还是大于指定的双精度浮点数的值。

    **语法:**

    ```cs
    public int CompareTo (double value);
    ```

    这里，需要一个双精度浮点数来进行比较。

    **返回值:**这个方法返回一个有符号的数字，表示这个实例和*值*的相对值。

    *   **小于零:**此实例小于值或此实例不是数字(NaN)，值是数字。
    *   **零:**此实例等于值，或者此实例和值都不是数字(NaN)、正数或负数。
    *   **大于零:**此实例大于值，或者此实例是数字，而值不是数字(NaN)。

    下面的程序说明了 *Double 的使用。比较(双)*方法:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Double.CompareTo(Double)
    // Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing value1
            double value1 = 10d;

            // Declaring and initializing value2
            double value2 = 20d;

            // compare both double value
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

    **Output:**

    ```cs
    10 is less than 20

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // Double.CompareTo(Double)
    // Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // calling get() method
            get(5d, 7d);
            get(5.5d, 4.5d);
            get(10d, 20d);
            get(7.5d, 19.5d);
        }

        // defining get() method
        public static void get(double value1,
                               double value2)
        {

            // compare both double value
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

    **Output:**

    ```cs
    5 is less than 7
    5.5 is greater than 4.5
    10 is less than 20
    7.5 is less than 19.5

    ```

    #### 双倍。比较对象方法

    **翻倍。CompareTo()** 方法用于将当前实例与指定对象进行比较，并返回一个整数，该整数指示当前实例的值是小于、等于还是大于指定对象的值。

    **语法:**

    ```cs
    public int CompareTo (object value);
    ```

    这里，它需要一个对象进行比较，或者为 null。

    **返回值:**这个方法返回一个有符号的数字，表示这个实例和*值*的相对值。

    *   **小于零:**此实例小于值或此实例不是数字(NaN)，值是数字。
    *   **零:**此实例等于值，或者此实例和值都不是数字(NaN)、正数或负数。
    *   **大于零:**此实例大于值，或者此实例是数字，而值不是数字(NaN)。

    **异常:**如果值不是 Double，则抛出**参数异常**。

    下面的程序说明了 *Double 的使用。比较(对象)*方法:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Double.CompareTo(object)
    // Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            try {

                // Declaring and initializing value1
                double value1 = 10d;

                // Declaring and initializing value2
                object value2 = 20d;

                // compare both double value
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
                Console.WriteLine("value2 must be double");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }
    ```

    **Output:**

    ```cs
    10 is less than 20

    ```

    **示例 2:** 适用于*参数异常*

    ```cs
    // C# program to demonstrate the
    // Double.CompareTo(object)
    // Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            try {

                // Declaring and initializing value1
                double value1 = 10d;

                // Declaring and initializing value2
                object value2 = 1 / 3;

                // compare both double value
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
                Console.WriteLine("value2 must be double");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }
    ```

    **Output:**

    ```cs
    value2 must be double
    Exception Thrown: System.ArgumentException

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . double . compare to？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.double.compareto?view=netframework-4.7.2)**