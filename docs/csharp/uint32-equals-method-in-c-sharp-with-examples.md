# UInt32。C# 中的 Equals 方法及示例

> 原文:[https://www . geesforgeks . org/uint 32-equals-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint32-equals-method-in-c-sharp-with-examples/)

**UInt32。Equals 方法**用于获取一个值，该值指示当前实例是否等于指定的对象或 32 位无符号整数。此方法的重载列表中有 2 种方法，如下所示:

*   **等于(UInt32)方法***   **Equals(Object) Method

    #### UInt32。等于(UInt32)方法

    此方法用于返回一个值，该值指示当前实例是否等于指定的 32 位无符号整数值。

    > **语法:**public bool Equals(uint obj)；
    > 这里，它需要一个 32 位无符号整数值来与当前实例进行比较。
    > 
    > **返回值:**如果*对象*与该实例具有相同的值，则该方法返回 *true* ，否则返回 false。

    以下程序说明了 *UInt32 的使用。等于(UInt32)* 方法:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // UInt32.Equals(UInt32) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing value1
            uint value1 = 5322;

            // Declaring and initializing value2
            uint value2 = 7328;

            // using Equals(UInt32) method
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
    5322 is not equal to 7328

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // UInt32.Equals(UInt32) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {

            // calling get() method
            get(9128, 1978);
            get(6455, 6455);
            get(10120, 10120);
            get(UInt32.MaxValue, UInt32.MinValue);
        }

        // defining get() method
        public static void get(uint value1,
                               uint value2)
        {

            // using Equals(UInt32) method
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
    9128 is not equal to 1978
    6455 is equal to 6455
    10120 is equal to 10120
    4294967295 is not equal to 0

    ```

    #### UInt32。等于(对象)方法

    此方法用于返回一个值，该值指示当前实例是否等于指定的对象。

    > **语法:**公共覆盖 bool Equals(对象 obj)；
    > 这里，需要一个对象与当前实例进行比较。
    > 
    > **返回值:**如果*对象*是 UInt32 的实例，并且等于该实例的值，则该方法返回 *true* ，否则返回 false。

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // UInt32.Equals(Object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing value1
            uint value1 = 11227;

            // Declaring and initializing value2
            object value2 = (uint)1 / 17;

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
    11227 is not equal to 0

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // UInt32.Equals(Object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // calling get() method
            get(11232, 7455);
            get(1412, 14314);
            get(7744, (uint)7744);
            get(54, 76);
        }

        // defining get() method
        public static void get(uint value1,
                             object value2)
        {

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
    11232 is not equal to 7455
    1412 is not equal to 14314
    7744 is equal to 7744
    54 is not equal to 76

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . uint 32 . equals？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint32.equals?view=netstandard-2.1)**