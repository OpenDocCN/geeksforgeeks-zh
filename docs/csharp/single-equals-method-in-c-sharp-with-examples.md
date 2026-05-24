# 单身。C# 中的 Equals()方法及示例

> 原文:[https://www . geesforgeks . org/single-equals-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/single-equals-method-in-c-sharp-with-examples/)

**单身。Equals()方法**用于获取一个值，该值指示 Single 的两个实例是否代表相同的值。此方法的重载列表中有 2 种方法，如下所示:

*   **相等(单一)方法***   **Equals(Object) Method

    #### 单身。相等(单一)方法

    此方法用于返回一个值，该值指示此实例和指定的 Single 对象是否表示相同的值。

    > **语法:**public bool Equals(float obj)；
    > 在这里，它需要一个单一的对象来比较这个实例。
    > 
    > **返回值:**如果 obj 等于该实例，则该方法返回*真*，否则返回*假*。

    以下程序说明了 **Single 的使用。Equals()** 方法:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Single.Equals(Single) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing value1
            float value1 = 10.5f;

            // Declaring and initializing value2
            float value2 = 20.6f;

            // using Equals(Single) method
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
    10.5 is not equal to 20.6

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // Single.Equals(Single) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {

            // calling get() method
            get(5f, 5f);
            get(5.5f, 4.5f);
            get(10f, 10f);
            get(7.5f, 19.5f);
        }

        // defining get() method
        public static void get(float value1, 
                               float value2)
        {

            // using Equals(Single) method
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
    5 is equal to 5
    5.5 is not equal to 4.5
    10 is equal to 10
    7.5 is not equal to 19.5

    ```

    #### 单身。等于(对象)方法

    此方法用于返回一个值，该值指示此实例是否等于指定的对象。

    > **语法:**公共覆盖 bool Equals(对象 obj)；
    > 在这里，需要一个对象来与这个实例进行比较。
    > 
    > **返回值:**如果*对象*是 Single 的实例，并且等于该实例的值，则该方法返回 *true* ，否则返回 false。

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Single.Equals(Single) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing value1
            float value1 = 10.5f;

            // Declaring and initializing value2
            object value2 = 3 / 36;

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
    10.5 is not equal to 0

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // Single.Equals(object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // calling get() method
            get(5f, new Object());
            get(5.5f, (float)5.5);
            get(10f, 10);
            get(7.5f, 2 / 5);
        }

        // defining get() method
        public static void get(float value1,
                             object value2)
        {

            // compare both float value
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
    5 is not equal to System.Object
    5.5 is equal to 5.5
    10 is not equal to 10
    7.5 is not equal to 0

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . single . equals？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.single.equals?view=netstandard-2.1)**