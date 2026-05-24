# UInt64。C# 中的 Equals 方法及示例

> 原文:[https://www . geesforgeks . org/uint 64-equals-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint64-equals-method-in-c-sharp-with-examples/)

**UInt64。Equals 方法**用于获取一个值，该值指示当前实例是否等于指定对象或 64 位无符号长整数。此方法的重载列表中有 2 种方法，如下所示:

*   **等于(UInt64)方法***   **Equals(Object) Method

    #### UInt64。等于(UInt64)方法

    此方法用于返回一个值，该值指示当前实例是否等于指定的 64 位无符号长整数值。

    > **语法:**public bool Equals(ulong obj)；
    > 这里，需要一个 64 位无符号长整数值与当前实例进行比较。
    > 
    > **返回值:**如果*对象*与该实例具有相同的值，则该方法返回 *true* ，否则返回 false。

    以下程序说明了 *UInt64 的使用。等于(UInt64)* 方法:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // UInt64.Equals(UInt64) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing value1
            ulong value1 = 5232642;

            // Declaring and initializing value2
            ulong value2 = 2317648;

            // using Equals(UInt64) method
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
    5232642 is not equal to 2317648

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // UInt64.Equals(UInt64) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {

            // calling get() method
            get(9213128, 2131978);
            get(656455, 656455);
            get(10120, 10120);
            get(UInt64.MaxValue, UInt64.MinValue);
        }

        // defining get() method
        public static void get(ulong value1,
                               ulong value2)
        {

            // using Equals(UInt64) method
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
    9213128 is not equal to 2131978
    656455 is equal to 656455
    10120 is equal to 10120
    18446744073709551615 is not equal to 0

    ```

    #### UInt64。等于(对象)方法

    此方法用于返回一个值，该值指示当前实例是否等于指定的对象。

    > **语法:**公共覆盖 bool Equals(对象 obj)；
    > 这里，需要一个对象与当前实例进行比较。
    > 
    > **返回值:**如果*对象*是 UInt64 的实例，并且等于该实例的值，则该方法返回 *true* ，否则返回 false。

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // UInt64.Equals(Object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing value1
            ulong value1 = 13421227;

            // Declaring and initializing value2
            object value2 = 1 / 417;

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
    13421227 is not equal to 0

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // UInt64.Equals(Object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // calling get() method
            get(1231264, 7234455);
            get(1423412, (ulong)14432314);
            get(7742344, (ulong)7742344);
            get(5443, 7346);
        }

        // defining get() method
        public static void get(ulong value1,
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
    1231264 is not equal to 7234455
    1423412 is not equal to 14432314
    7742344 is equal to 7742344
    5443 is not equal to 7346

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . uint 64 . equals？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint64.equals?view=netstandard-2.1)**