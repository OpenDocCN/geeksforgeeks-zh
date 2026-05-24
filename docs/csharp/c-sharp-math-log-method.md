# C# |数学。Log()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-math-log-method/](https://www.geeksforgeeks.org/c-sharp-math-log-method/)

在 C# 中 ***数学。*log()**是一个数学类的方法。它用于返回指定数字的对数。通过更改传递的参数数量，可以重载此方法。*数学的过载列表中总共有 2 种方法。Log()* 方法如下:

*   **数学。对数(双)法***   **Math.Log(Double, Double) Method

    ##### 数学。对数(双)法

    此方法用于返回指定数字的自然对数(以 e 为底)。

    **语法:**

    ```cs
    public static double Log(double val)
    ```

    **参数:**

    > **val:** 是要计算其自然(以 e 为底)对数的指定数，其类型为*系统。双*。

    **返回值:**返回*值*的自然对数，类型为*系统。双*。

    **注意:**参数*值*始终指定为基数 10。返回值取决于传递的参数。以下是一些案例:

    *   如果参数为*正*，则方法将返回自然对数或**对数 <sub>e</sub> (val)** 。
    *   如果参数是*零*，那么结果就是*否定*。
    *   如果参数为*负(小于零)*或等于 *NaN* ，则结果为 *NaN* 。
    *   如果参数是*正定性*，那么结果就是*正定性*。
    *   如果论证是*否定*，那么结果就是*楠*。

    **示例:**

    ```cs
    // C# program to demonstrate working
    // of Math.Log(Double) method
    using System;

    class Geeks {

        // Main Method
        public static void Main(String[] args)
        {

            // double values whose logarithm 
            // to be calculated
            double a = 4.55;
            double b = 0;
            double c = -2.45;
            double nan = Double.NaN;
            double positiveInfinity = Double.PositiveInfinity;       
            double negativeInfinity = Double.NegativeInfinity;

            // Input is positive number so output
            // will be logarithm of number
            Console.WriteLine(Math.Log(a));

            // positive zero as argument, so output 
            // will be -Infinity
            Console.WriteLine(Math.Log(b));

            // Input is negative number so output
            // will be NaN
            Console.WriteLine(Math.Log(c));

            // Input is NaN so output
            // will be NaN
            Console.WriteLine(Math.Log(nan));

            // Input is PositiveInfinity so output
            // will be Infinity
            Console.WriteLine(Math.Log(positiveInfinity));

            // Input is NegativeInfinity so output
            // will be NaN
            Console.WriteLine(Math.Log(negativeInfinity));
        }
    }
    ```

    **Output:**

    ```cs
    1.51512723296286
    -Infinity
    NaN
    NaN
    Infinity
    NaN

    ```

    ##### 数学。对数(双，双)法

    此方法用于返回指定底数中指定数字的对数。

    **语法:**

    ```cs
    public static double Log(double val, double base)
    ```

    **参数:**

    > **val:** 是要计算对数的指定数字，类型为*系统。双*。
    > 
    > **底数:**是*系统类型对数的底数。双*。

    **返回值:**返回*值*的对数，类型为*系统。双*。

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
    // of Math.Log(Double, Double) method
    using System;

    class Geeks {

        // Main Method
        public static void Main(String[] args)
        {

            // Here val = 1.3 and base is 0.3 then 
            // output will be logarithm of given value
            Console.WriteLine(Math.Log(1.3, 0.3));

            // Here val is 0.5 and base > 1 then output 
            // will be -0.5
            Console.WriteLine(Math.Log(0.5, 4));

            // Here val is 0.7 and base = 1 then output 
            // will be NaN
            Console.WriteLine(Math.Log(0.7, 1));

            // Here val is 0.7 and base is NaN then output 
            // will be NaN
            Console.WriteLine(Math.Log(0.7, Double.NaN));
        }
    }
    ```

    **Output:**

    ```cs
    -0.217915440884381
    -0.5
    NaN
    NaN

    ```

    **参考文献:**

    *   [https://msdn . Microsoft . com/en-us/library/x80ywz41(v = vs . 110)。aspx](https://msdn.microsoft.com/en-us/library/x80ywz41(v=vs.110).aspx)
    *   [https://msdn . Microsoft . com/en-us/library/HD 50b 6 H5(v = vs . 110)。aspx](https://msdn.microsoft.com/en-us/library/hd50b6h5(v=vs.110).aspx)**