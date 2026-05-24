# MathF。C# 中的 Round()方法，带示例| Set–2

> 原文:[https://www . geesforgeks . org/mathf-round-method-in-c-sharp-with-examples-set-2/](https://www.geeksforgeeks.org/mathf-round-method-in-c-sharp-with-examples-set-2/)

在 C# 中 ***MathF。Round()*** 是一个 MathF 类方法，用于将一个值舍入到最接近的整数或小数位数。它返回数字的最近值，精度等于传递的第二个参数。如果要舍入的值正好介于偶数和奇数之间，则返回偶数。*马瑟夫。第*轮适用于 IEEE 标准 754，第 4 节。通过更改传递的参数的数量和类型，可以重载此方法。 *MathF 的过载列表中有 4 种方法。回合()*方法如下:

*   **MathF。圆(单)法***   **MathF。圆形(单一，整数 32)方法***   **MathF。舍入(单一、整数 32、中点舍入)方法***   **MathF.Round(Single, MidpointRounding) Method

    在这里，我们将讨论最后两种方法。

    #### 数学。舍入(单一、整数 32、中点舍入)方法

    此方法用于将单精度浮点值舍入到指定的小数位数。参数指定如果值在两个数字中间，如何舍入该值。

    > **语法:**公共静态浮点 Round (float x，int 位数，中点舍入模式)；
    > 
    > **参数:**
    > 
    > **x** :需要四舍五入的单精度浮点数，此参数类型为*系统。单*。
    > 
    > **位数**:是返回值中的小数位数，该参数类型为*系统。Int32* 。
    > 
    > **模式**:如果在另外两个数字中间，作为*中点舍入*的话，如何舍入 **x** 的规范。

    **返回类型:**该方法返回最接近 *x* 的数字，其小数位数等于*位数*。如果 *x* 的小数位数比*的小数位数*少，则 x 不变地返回。该方法的返回类型为*系统。单*。

    **异常:**

    *   *argumentout of range exception*:如果*数字*小于 0 或大于 15。
    *   *参数异常*:如果*模式*不是中点舍入的有效值。

    **示例:**

    ```cs
    // C# program to demonstrate the
    // MathF.Round(Single, Int32,
    // MidpointRounding) method
    using System;

    class Geeks {

        // Main Method
        public static void Main()
        {
            // The 4 values are store in an float
            // type array name 'val'
            float[] x = { 8.115f, 7.135f, 9.165f, 6.175f };

            Console.WriteLine("Rounded values are:");

            // 'foreach' loop iterates through
            // each item from the array 'values'
            // and storing the items in a new
            // variable 'x'
            foreach(float value in x)

                // '{0}' specify the variable 'x' which is
                // in 'foreach' loop and '{1}' specify the
                // rounded value, here '2' defines the number
                // of digit after point, e.g. 4.135f == 4.14f,
                // after '4f.' there is 2 digits'.14f'
                // and here '.ToEven' select the nearest even
                // number e.g 4.125f == 4.12f, here nearest even
                // number is '12f',
                Console.WriteLine("{0} == {1}", value, MathF.Round(value, 2,
                                                  MidpointRounding.ToEven));
        }
    }
    ```

    **Output:**

    ```cs
    Rounded values are:
    8.115 == 8.12
    7.135 == 7.14
    9.165 == 9.16
    6.175 == 6.18

    ```

    #### MathF。舍入(单点、中点舍入)方法

    此方法用于将单精度浮点值舍入到最接近的整数。参数指定如果值在两个数字中间，如何舍入该值。

    > **语法:**公共静态浮点 Round (float x，MidpointRounding 模式)；
    > 
    > **参数:**
    > 
    > **x** :需要四舍五入的单精度浮点数，此参数类型为*系统。单*。
    > 
    > **模式**:如果在另外两个数字中间，作为*中点舍入*的话，如何舍入 **x** 的规范。

    **返回类型:**该方法返回最接近的整数值。如果 *x* 在两个整数中间，其中一个是偶数，另一个是奇数，那么模式决定返回两者中的哪一个。这种方法的返回类型是*系统。单*。

    **异常:**如果*模式*不是中点舍入的有效值，此方法给出*参数异常*。

    **示例:**

    ```cs
    // C# program to demonstrate the
    // MathF.Round(Single, MidpointRounding) 
    // method
    using System;

    class Geeks {

        // Main Method
        public static void Main()
        {

            // 'x' is float type variable
            // which holds the value 7.1f
            float x = 7.1f;

            Console.WriteLine("Inside Loop:\n");

            //'for loop', it execute the next
            // output for 8 times
            for (int i = 0; i <= 8; i++) {

                // '{0}' specify the variable 'x' and
                // '{1}' specify the rounded value
                Console.WriteLine("{0} = {1}", x, MathF.Round(x,
                                MidpointRounding.AwayFromZero));

                // increment 'x' by '0.1'
                x += 0.1f;
            }

            // a new value is assigned
            // to variable 'x'
            x = 4.5f;

            // prints a new line
            Console.WriteLine();

            //'{0}'specify the variable 'x' in which a new
            // value 4.5f is assigned and '{1}' specify the
            // new rounded value
            Console.WriteLine("Outside Loop : {0} = {1}", x,
              MathF.Round(x, MidpointRounding.AwayFromZero));
        }
    }
    ```

    **Output:**

    ```cs
    Inside Loop:

    7.1 = 7
    7.2 = 7
    7.3 = 7
    7.4 = 7
    7.5 = 7
    7.599999 = 8
    7.699999 = 8
    7.799999 = 8
    7.899999 = 8

    Outside Loop : 4.5 = 5

    ```**