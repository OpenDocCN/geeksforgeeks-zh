# C# |带示例的数学类字段

> 原文:[https://www . geeksforgeeks . org/c-sharp-math-class-field-with-examples/](https://www.geeksforgeeks.org/c-sharp-math-class-fields-with-examples/)

在 C# 中，数学类为对数函数、三角函数和其他数学函数提供常数和静态方法。数学类有如下两个字段:

*   数学。电场
*   数学。π场

#### 

数学。电场

此字段表示自然对数基数，由常数 e 指定。

**语法:**

```cs
public const double E

```

**程序 1:** 说明数学。数学课上的电场

```cs
// C# program to demonstrate the
// Constant values of Math.E function
using System;

class GFG {

    // Main method
    static void Main()
    {

        // To find E constant values
        double e = Math.E;

        // Print result
        Console.WriteLine("Math.E  = " + e);
    }
}
```

**Output:**

```cs
Math.E  = 2.71828182845905

```

**程序 2:** 我们来看一个比较数学的例子。e 用幂级数计算的值。

```cs
// C# program to demonstrate the to
// find the values of Math.E field
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Initialize the data
        double fact = 1.0;
        double PS = 0.0;

        // for loop run until the absolute
        // values condition satified
        for (int n = 0; n < 10 && 
             Math.Abs(Math.E - PS) > 1.0E-15; n++) 
        {

            // Calculate the factorial
            if (n > 0)
                // update factorial
                fact *= (double)n;

            // Calculate the power series.
            PS += 1.0 / fact;

            // Display the power series result
            Console.WriteLine(PS);
            Console.WriteLine(Math.E - PS);
        }
    }
}
```

**Output:**

```cs
1
1.71828182845905
2
0.718281828459045
2.5
0.218281828459045
2.66666666666667
0.0516151617923786
2.70833333333333
0.00994849512571205
2.71666666666667
0.00161516179237875
2.71805555555556
0.000226272903489644
2.71825396825397
2.7860205076724E-05
2.71827876984127
3.05861777505356E-06
2.71828152557319
3.02885852843104E-07

```

#### 

数学。π场

它表示圆的周长与直径的比值，由常数π指定。

**语法:**

```cs
public const double PI

```

**程序 1:** 说明数学。数学课中的圆周率字段

```cs
// C# program to demonstrate the
// Constant values of Math.PI function
using System;

class GFG
{
    // Main method 
    static void Main()
    {

        // To find PI constant values
        double pi_value = Math.PI; 

        // Print result
        Console.WriteLine("Math.PI = " + pi_value);
    }
} 
```

**Output:**

```cs
Math.PI = 3.14159265358979

```

**程序 2:** 用数学演示不同数据类型的乘法运算。PI 常数值。

```cs
// C# program to demonstrate the
// Constant values of Math.PI function
using System;

class GFG
{
    // Main method 
    static void Main()
    {
        // Multiply int ,float,negative number with
        // Math.PI and display  result
        Console.WriteLine(1 * Math.PI );

        Console.WriteLine(2 * Math.PI );

        Console.WriteLine(1.5 * Math.PI );

        Console.WriteLine(-3.10 * Math.PI );
    }
} 
```

**Output:**

```cs
3.14159265358979
6.28318530717959
4.71238898038469
-9.73893722612836

```

**程序 3:** 我们来演示 PI 的访问，求出圆柱体的体积。

```cs
// C# program to demonstrate the
// Constant values of Math.PI function
using System;

class GFG {

    // Main method 
    static void Main()
    {

          // input radius value
          double radius = 6;

          // input length value
           double length = 9;

           // calculate the area using PI
           double area = radius * radius * Math.PI;

           // Calculate volume
           double volume = area * length;

           // print area and volume of cylinder 
           Console.WriteLine("Area of cylinder is : " + area);
           Console.WriteLine("Volume of cylinder is : " + volume);
  }
}
```

**Output:**

```cs
Area of cylinder is : 113.097335529233
Volume of cylinder is : 1017.87601976309

```

**参考文献:**

*   [https://msdn . Microsoft . com/en-us/library/system . math . e(v = vs . 110)。aspx](https://msdn.microsoft.com/en-us/library/system.math.e(v=vs.110).aspx)
*   [https://msdn . Microsoft . com/en-us/library/system . math . pi(v = vs . 110)。aspx](https://msdn.microsoft.com/en-us/library/system.math.pi(v=vs.110).aspx)