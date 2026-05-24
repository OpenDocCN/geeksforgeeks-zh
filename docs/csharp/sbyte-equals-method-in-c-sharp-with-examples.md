# SByte。C# 中的 Equals 方法及示例

> 原文:[https://www . geesforgeks . org/sbyte-equals-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/sbyte-equals-method-in-c-sharp-with-examples/)

**SByte。Equals 方法**用于获取一个值，该值指示当前实例是否等于指定的对象或字节。此方法的重载列表中有 2 种方法，如下所示:

*   **相等(字节)法***   **Equals(Object) Method

    #### SByte。相等(字节)法

    此方法用于返回一个值，该值指示当前实例是否等于指定的 SByte 值。

    > **语法:**public bool Equals(sbyte obj)；
    > 这里，需要一个 SByte 值来与当前实例进行比较。
    > 
    > **返回值:**如果*对象*与该实例具有相同的值，则该方法返回 *true* ，否则返回 false。

    下面的程序说明了 *SByte 的使用。等于(字节)*方法:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // SByte.Equals(SByte) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing value1
            sbyte value1 = 42;

            // Declaring and initializing value2
            sbyte value2 = 23;

            // using Equals(SByte) method
            bool status = value1.Equals(value2);

            // checking the status
            if (status)
                Console.WriteLine("{0} is equal to {1}",
                                        value1, value2);
            else
                Console.WriteLine("{0} is not equal to {1}",
                                            value1, value2);
        }
    }
    ```

    **Output:**

    ```cs
    42 is not equal to 23

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // SByte.Equals(SByte) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {

            // calling get() method
            get(78, 58);
            get(45, 45);
            get(10, 20);
            get(SByte.MaxValue, SByte.MinValue);
        }

        // defining get() method
        public static void get(sbyte value1,
                               sbyte value2)
        {

            // using Equals(SByte) method
            bool status = value1.Equals(value2);

            // checking the status
            if (status)
                Console.WriteLine("{0} is equal to {1}",
                                        value1, value2);
            else
                Console.WriteLine("{0} is not equal to {1}",
                                            value1, value2);
        }
    }
    ```

    **Output:**

    ```cs
    78 is not equal to 58
    45 is equal to 45
    10 is not equal to 20
    127 is not equal to -128

    ```

    #### SByte。等于(对象)方法

    此方法用于返回一个值，该值指示当前实例是否等于指定的对象。

    > **语法:**公共覆盖 bool Equals(对象 obj)；
    > 这里，需要一个对象与当前实例进行比较。
    > 
    > **返回值:**如果*对象*是 SByte 的实例，并且等于该实例的值，则该方法返回 *true* ，否则返回 false。

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // SByte.Equals(Object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing value1
            sbyte value1 = 10;

            // Declaring and initializing value2
            object value2 = 1 / 47;

            // using Equals(object) method
            bool status = value1.Equals(value2);

            // checking the status
            if (status)
                Console.WriteLine("{0} is equal to {1}",
                                        value1, value2);
            else
                Console.WriteLine("{0} is not equal to {1}",
                                            value1, value2);
        }
    }
    ```

    **Output:**

    ```cs
    10 is not equal to 0

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // SByte.Equals(Object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // calling get() method
            get(112, 85);
            get(124, 154);
            get(87, 87);
            get(54, 76);
        }

        // defining get() method
        public static void get(sbyte value1,
                            object value2)
        {

            // compare both SByte value
            // using Equals(object) method
            bool status = value1.Equals(value2);

            // checking the status
            if (status)
                Console.WriteLine("{0} is equal to {1}",
                                        value1, value2);
            else
                Console.WriteLine("{0} is not equal to {1}",
                                            value1, value2);
        }
    }
    ```

    **Output:**

    ```cs
    112 is not equal to 85
    124 is not equal to 154
    87 is not equal to 87
    54 is not equal to 76

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . sbyte . equals？view=netcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.sbyte.equals?view=netcore-2.1)**