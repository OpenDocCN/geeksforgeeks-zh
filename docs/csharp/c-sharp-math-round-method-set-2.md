# C# |数学。Round()方法| Set–2

> 原文:[https://www . geesforgeks . org/c-sharp-math-round-method-set-2/](https://www.geeksforgeeks.org/c-sharp-math-round-method-set-2/)

在 C# 中 ***数学。Round()*** 是一种数学类方法，用于将一个值舍入到最接近的整数或小数位数。此方法还有另一个重载，使用该重载，您可以指定返回值小数点后的位数。它返回数字的最近值，精度等于传递的第二个参数。如果要舍入的值正好介于偶数和奇数之间，则返回偶数。*数学。第*轮适用于 IEEE 标准 754，第 4 节。

通过更改传递的参数的数量和类型，可以重载此方法。*数学的重载列表中总共有 8 种方法。Round()* 方法其中 **4** 已经在 **[C# | Math 中讨论过了。Round()方法| Set–1](https://www.geeksforgeeks.org/c-math-round-method-set-1/)**。

*   **[数学。圆形(双)](https://www.geeksforgeeks.org/c-math-round-method-set-1/)***   **[数学。圆形(双面，国际号码 32)](https://www.geeksforgeeks.org/c-math-round-method-set-1/)***   **[数学。四舍五入(十进制)](https://www.geeksforgeeks.org/c-math-round-method-set-1/)***   **[数学。四舍五入(十进制，整数 32)](https://www.geeksforgeeks.org/c-math-round-method-set-1/)***   **数学。舍入(双精度，整数 32，中点舍入)***   **数学。圆形(双点、中点圆形)***   **数学。舍入(十进制，整数 32，中点舍入)***   **Math.Round(Decimal, MidpointRounding)

    #### 数学。舍入(双精度，整数 32，中点舍入)

    此方法用于将双精度浮点值舍入到指定的小数位数。参数指定如果值在两个数字中间，如何舍入该值。

    **语法:**

    ```cs
    public static double Round (double val, int digits, MidpointRounding mode);

    ```

    **参数:**

    > **值**:需要四舍五入的双精度浮点数，该参数类型为*系统。双*。
    > 
    > **位数**:是返回值中的小数位数，该参数类型为*系统。Int32* 。
    > 
    > **模式**:如果在另外两个数字中间，作为*中点舍入*如何舍入**值的规范。**

    **返回类型:**该方法返回最接近*值*的数字，其小数位数等于*位数*。如果 *val* 的小数位数少于*的小数位数*，则 val 不变地返回。该方法的返回类型为*系统。双*。

    **异常:**

    *   *argumentout of range exception*:如果*数字*小于 0 或大于 15。
    *   *参数异常*:如果*模式*不是中点舍入的有效值。

    **示例:**

    ```cs
    // C# program to demonstrate the 
    // Math.Round(Double, Int32, 
    // MidpointRounding) method
    using System;

    class Geeks 
    {

        // Main Method
        public static void Main() 
        {
            // The 4 values are store in an double
            // type array name 'val'
            double[] val = {4.125, 4.135, 4.165, 4.175};

            Console.WriteLine("Rounded values are:"); 

            // 'foreach' loop iterates through
            // each item from the array 'values' 
            // and storing the items in a new 
            // variable 'val' 
            foreach(double value in val) 

                // '{0}' specify the variable 'val' which is
                // in 'foreach' loop and '{1}' specify the 
                // rounded value, here '2' defines the number
                // of digit after point, e.g. 4.135 == 4.14,
                // after '4.' there is 2 digits'.14' 
                // and here '.ToEven' select the nearest even
                // number e.g 4.125 == 4.12, here nearest even
                // number is '12',
                Console.WriteLine("{0} == {1}", value, Math.Round(value, 2, 
                                                 MidpointRounding.ToEven));

        }
    }
    ```

    **Output:**

    ```cs
    Rounded values are:
    4.125 == 4.12
    4.135 == 4.14
    4.165 == 4.16
    4.175 == 4.18

    ```**