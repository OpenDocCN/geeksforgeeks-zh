# C# |随机。下一个()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-random-next-method/](https://www.geeksforgeeks.org/c-sharp-random-next-method/)

**系统的 **Next()** 方法。C# 中的 Random** 类用于获取随机整数。这个方法可以通过传递不同的参数来重载，如下所示:

*   **下一个()***   **下一个(国际号码 32)***   **Next(Int32, Int32)

    #### 下一个()方法

    此方法用于返回非负随机整数。

    **语法:**

    ```cs
    public virtual int Next ();
    ```

    **返回值:**该方法返回大于等于 0 且小于*最大值*的 32 位有符号整数。

    **示例:**

    ```cs
    // C# program to illustrate the 
    // Random.Next() Method
    using System;

    class GFG {

        // Driver code
        public static void Main()
        {
            // Instantiate random number generator
            Random rand = new Random();

            // Print 10 random numbers
            Console.WriteLine("Printing 10 random numbers");
            for (int i = 1; i <= 10; i++)
                Console.WriteLine("{0} -> {1}", i, rand.Next());
        }
    }
    ```

    **Output:**

    ```cs
    Printing 10 random numbers
    1 -> 1386420123
    2 -> 2133003862
    3 -> 981665925
    4 -> 495382685
    5 -> 1127976381
    6 -> 824414652
    7 -> 213006792
    8 -> 1948108820
    9 -> 214839986
    10 -> 261560448

    ```

    #### 下一个(Int32)方法

    此方法用于获取小于指定最大值的非负随机整数。

    **语法:**

    ```cs
    public virtual int Next (int maxValue);
    ```

    这里， *maxValue* 是要生成的随机数的上边界。它必须大于或等于 0。

    **返回值:**该函数返回一个大于等于 0 且小于*最大值*的 32 位有符号整数。但是，如果*最大值*等于 0，则返回*最大值*。

    **异常:**如果*最大值*小于 0，此方法将给出*argumentout of range Exception*。

    **示例:**

    ```cs
    // C# program to illustrate the
    // Random.Next(Int32) Method
    using System;

    class GFG {

        // Driver code
        public static void Main()
        {
            // Instantiate random number generator
            Random rand = new Random();

            // Print 10 random numbers less than 100
            Console.WriteLine("Printing 10 random numbers less than 100");
            for (int i = 1; i <= 10; i++)
                Console.WriteLine("{0} -> {1}", i, rand.Next(100));
        }
    }
    ```

    **Output:**

    ```cs
    Printing 10 random numbers less than 100
    1 -> 19
    2 -> 94
    3 -> 14
    4 -> 54
    5 -> 94
    6 -> 73
    7 -> 39
    8 -> 42
    9 -> 18
    10 -> 77

    ```

    #### 下一个(Int32，Int32)方法

    此方法用于获取指定范围内的随机整数。

    **语法:**

    ```cs
    public virtual int Next (int minValue, int maxValue);
    ```

    **参数:**

    *   *maxValue:* 是生成随机数的排他上界。它必须大于或等于 minValue。
    *   *minValue:* 是返回的随机数的包含下界。

    **返回值:**该函数返回一个大于或等于*最小值*且小于*最大值*的 32 位有符号整数；即返回值的范围包括 *minValue* 但不包括 *maxValue* 。如果*最小值*等于*最大值*，则返回*最小值*。

    **异常:**如果*最小值*大于*最大值*，此方法将给出*参数。*

    **示例:**

    ```cs
    // C# program to illustrate the
    // Next(Int32, Int32) Method
    using System;

    class GFG {

        // Driver code
        public static void Main()
        {
            // Instantiate random number generator
            Random rand = new Random();

            // Print 10 random numbers between 50 and 100
            Console.WriteLine("Printing 10 random numbers"+
                                    " between 50 and 100");
            for (int i = 1; i <= 10; i++)
                Console.WriteLine("{0} -> {1}", i, rand.Next(50, 100));
        }
    }
    ```

    **Output:**

    ```cs
    Printing 10 random numbers between 50 and 100
    1 -> 91
    2 -> 85
    3 -> 93
    4 -> 74
    5 -> 88
    6 -> 77
    7 -> 92
    8 -> 76
    9 -> 77
    10 -> 52

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . random . next？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.random.next?view=netframework-4.7.2)**