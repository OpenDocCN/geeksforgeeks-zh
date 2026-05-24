# 翻倍。C# 中的 IsNaN()方法

> 原文:[https://www . geesforgeks . org/double-isnan-method-in-c-sharp/](https://www.geeksforgeeks.org/double-isnan-method-in-c-sharp/)

在 C# 中 ***加倍。*IsNaN()**是一种双重结构方法。此方法用于检查指定的值是否不是数字(NaN)。

> **语法:**公共静态 bool IsNaN(double d)；
> 
> **参数:**
> *d* :是 System 类型的双精度浮点数。两倍

**返回类型:**该函数返回布尔值，即*真*，如果指定值不是数字(NaN)，则返回*假*。

**示例:**

```cs
Input  : d = 0.0 / 0.0 
Output : True

Input  : d = 1.734
Output : False

```

**代码:**演示替身。IsNaN(Double)方法。

```cs
// C# code to demonstrate 
// Double.IsNaN(Double) method 
using System;

class GFG { 

    // Main Method
    public static void Main(String[] args) 
    { 

        // first example 
        Double f1 = 1.0 / 0.0; 

        bool res = Double.IsNaN(f1); 

        // printing the output 
        if (res) 
            Console.WriteLine(f1 + " is NaN"); 
        else
            Console.WriteLine(f1 + " is not NaN"); 

        // second example 
        double f2 = 0.0 / 0.0; 

        bool res1 = Double.IsNaN(f2); 

        // printing the output 
        if (res1) 
            Console.WriteLine(f2 + " is NaN"); 
        else
            Console.WriteLine(f2 + " is not NaN"); 
    } 
} 
```

**Output:**

```cs
Infinity is not NaN
NaN is NaN

```

**注:**

*   如果我们将任何值直接除以 0，编译器将显示一个错误。因此，在上面的例子中，0 首先存储在一个变量中。
*   每个浮点操作都返回一个 NaN，以表明操作的结果是未定义的。