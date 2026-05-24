# C# |数学。Atan2()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-math-atan2-method/](https://www.geeksforgeeks.org/c-sharp-math-atan2-method/)

***数学。Atan2()*** 是一个内置的数学类方法，它返回正切为两个指定数字的商的角度。基本上，它返回一个角度θ(以弧度测量)，其值介于-π和π之间。这是正 x 轴和点(x，y)之间的逆时针角度。

**语法:**

```cs
public static double Atan2(double value1, double value2)

```

**参数:**

> **值 1:** 类型点的 y 坐标*系统。双*。
> **值 2:** 类型点的 x 坐标*系统。双*。

**返回类型:**返回类型*系统的角度θ。双*。

**注:**一个角度θ(以弧度测量)，使得-π ≤ θ ≤ π，tan(θ) = value1 / value2，其中(value1，value2)是笛卡尔平面中的点。返回值有两个条件:

*   当点位于笛卡尔平面时
*   当点位于象限的边界上时

下面是演示数学的程序。当点*位于笛卡尔平面*时的方法:

*   **程序 1:** 如果点(值 1，值 2)位于第一象限，即 0<θ<π/2

    ```cs
    // C# program to demonstrate the
    // Math.Atan2() Method when point
    // lies in first quadrant
    using System;

    class Geeks {

        // Main method
        public static void Main()
        {
            // using Math.Atan2() Method &
            // converting result into degree
            Console.Write(Math.Atan2(10, 10) * (180 / Math.PI));
        }
    }
    ```

    T5【输出:

    ```cs
    45

    ```

*   **程序 2:** 如果点(值 1，值 2)位于第二象限，即π/2<θ≤π

    ```cs
    // C# program to demonstrate the
    // Math.Atan2() Method when point
    // lies in second quadrant
    using System;

    class Geeks {

        // Main method
        public static void Main()
        {
            // using Math.Atan2() Method &
            // converting result into degree
            Console.Write(Math.Atan2(10, -10) * (180 / Math.PI));
        }
    }
    ```

    T5】输出:

    ```cs
    135

    ```

    T7】
*   **程序 3:** 如果点(值 1，值 2)位于第三象限，即-π<θ<-π/2

    ```cs
    // C# program to demonstrate the
    // Math.Atan2() Method when point
    // lies in third quadrant
    using System;

    class Geeks {

        // Main method
        public static void Main()
        {
            // using Math.Atan2() Method &
            // converting result into degree
            Console.Write(Math.Atan2(-10, -10) * (180 / Math.PI));
        }
    }
    ```

    T5【输出:

    ```cs
    -135

    ```

*   **程序 4:** 如果点(值 1，值 2)位于第四象限，即-π/2<θ<0

    ```cs
    // C# program to demonstrate the
    // Math.Atan2() Method when point
    // lies in fourth quadrant
    using System;

    class Geeks {

        // Main method
        public static void Main()
        {
            // using Math.Atan2() Method &
            // converting result into degree
            Console.Write(Math.Atan2(-10, 10) * (180 / Math.PI));
        }
    }
    ```

    T5】输出:

    ```cs
    -45

    ```

下面是演示数学的程序。当点*位于象限*的边界上时的方法:

*   **程序 1:** 如果值 1 为 0 且值 2 不为负，即θ = 0

    ```cs
    // C# program to demonstrate the
    // Math.Atan2() Method when value1 
    // is 0 and value2 is not negative
    using System;

    class Geeks {

        // Main method
        public static void Main()
        {
            // using Math.Atan2() Method &
            // converting result into degree
            Console.Write(Math.Atan2(0, 10) * (180 / Math.PI));
        }
    }
    ```

    **输出:**

```cs
0

```