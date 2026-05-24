# MathF。C# 中的 Log()方法及示例

> 原文:[https://www . geesforgeks . org/mathf-log-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-log-method-in-c-sharp-with-examples/)

在 C# 中 ***MathF。*log()**是一个 MathF 类的方法。它用于返回指定数字的对数。通过更改传递的参数数量，可以重载此方法。 *MathF 的过载列表中总共有 2 种方法。Log()* 方法如下:

*   **MathF。日志(单一)方法***   **MathF.Log(Single, Single) Method

    #### MathF。日志(单一)方法

    此方法用于返回指定数字的自然对数(以 e 为底)。

    > **语法:**公共静态 float Log(float x)；
    > 此处， **x** 为待计算自然对数(以 e 为底)的指定数，类型为*系统。单*。

    **返回值:**返回 *x* 的自然对数，类型为*系统。单*。

    **注意:**参数 *x* 始终指定为 10 进制数。返回值取决于传递的参数。以下是一些案例:

    *   如果参数为*正*，则方法将返回自然对数或**对数 <sub>e</sub> (val)** 。
    *   如果参数是*零*，那么结果就是*否定*。
    *   如果参数为*负(小于零)*或等于 *NaN* ，则结果为 *NaN* 。
    *   如果参数是*正定性*，那么结果就是*正定性*。
    *   如果论证是*否定*，那么结果就是*楠*。

    **示例:**

    ```cs
    // C# program to demonstrate working
    // of MathF.Log(Single) method
    using System;

    class Geeks {

        // Main Method
        public static void Main(String[] args)
        {

            // Single values whose logarithm
            // to be calculated
            float a = 9.78f;
            float b = 0f;
            float c = -4.56f;
            float nan = Single.NaN;
            float positiveInfinity = Single.PositiveInfinity;
            float negativeInfinity = Single.NegativeInfinity;

            // Input is positive number so output
            // will be logarithm of number
            Console.WriteLine(MathF.Log(a));

            // positive zero as argument, so output
            // will be -Infinity
            Console.WriteLine(MathF.Log(b));

            // Input is negative number so output
            // will be NaN
            Console.WriteLine(MathF.Log(c));

            // Input is NaN so output
            // will be NaN
            Console.WriteLine(MathF.Log(nan));

            // Input is PositiveInfinity so output
            // will be Infinity
            Console.WriteLine(MathF.Log(positiveInfinity));

            // Input is NegativeInfinity so output
            // will be NaN
            Console.WriteLine(MathF.Log(negativeInfinity));
        }
    }
    ```

    **Output:**

    ```cs
    2.280339
    -Infinity
    NaN
    NaN
    Infinity
    NaN

    ```

    #### 数学。日志(单一、单一)方法

    此方法用于返回指定底数中指定数字的对数。

    > **语法:**公共静态 float Log (float x，float y)；
    > 
    > **参数:**
    > **x:** 是要计算对数的指定数字，类型为*系统。单*。
    > **y:** 是*系统类型对数的底数。单*。

    **返回值:**返回 *x* 的对数，类型为*系统。单*。

    **注意:**返回值始终取决于传递的参数。下表描述了不同的情况:

    | 英国压力单位 | 基础 | 回收价值 |
    | --- | --- | --- |
    | val > 0 | (0 < Base < 1) or(Base > 1) | log〔t0〕基〔t1〕基 val |
    | val < 0 | 任何值 | 圆盘烤饼 |
    | 任何值 | 基数< 0 | 圆盘烤饼 |
    | 瓦尔。= 1 | base = 0 | 圆盘烤饼 |
    | 瓦尔。= 1 | base = +ve Infinity | 圆盘烤饼 |
    | 跌倒 = 楠 | 任何值 | 圆盘烤饼 |
    | 任何值 | base = NaN | 圆盘烤饼 |
    | 任何值 | 基数= 1 | 圆盘烤饼 |
    | val = 0 | (0 | +ve Infinity |
    | val = 0 | 基数> 1 | -ve Infinity |
    | val =+go 无穷大 | (0 | -ve Infinity |
    | val =+go 无穷大 | 基数> 1 | +ve Infinity |
    | val = 1 | base = 0 | Zero |
    | val = 1 | base = +ve Infinity | Zero |

    **示例:**

    ```cs
    // C# program to demonstrate working
    // of MathF.Log(Single, Single) method
    using System;

    class Geeks {

        // Main Method
        public static void Main(String[] args)
        {

            // Here val = 4.4f and base is 0.4f then
            // output will be logarithm of given value
            Console.WriteLine(MathF.Log(4.4f, 0.4f));

            // Here val is 0.5f and base > 1f then output
            // will be -0.5f
            Console.WriteLine(MathF.Log(0.5f, 4f));

            // Here val is 0.9f and base = 1f then output
            // will be NaN
            Console.WriteLine(MathF.Log(0.9f, 1f));

            // Here val is 0.4f and base is NaN then output
            // will be NaN
            Console.WriteLine(MathF.Log(0.4f, Single.NaN));
        }
    }
    ```

    **Output:**

    ```cs
    -1.616959
    -0.5
    NaN
    NaN

    ```**