# 小数。C# 中的 Compare()方法

> 原文:[https://www . geesforgeks . org/decimal-compare-method in-c-sharp/](https://www.geeksforgeeks.org/decimal-compare-method-in-c-sharp/)

此方法用于比较两个指定的十进制值。

> **语法:**公共静态 int Compare(十进制 a1，十进制 a2)；
> 
> **参数:**
> **a1** :此参数指定第一个要比较的值。
> **a2** :该参数指定第二个比较值。
> 
> **返回值**:返回一个带符号的数字，表示 a1 & a2 的相对值。
> 
> *   如果数值**小于零**，则表示 *a1* 小于 *a2* 。
> *   如果数值**大于零**，则表示 *a1* 大于 *a2* 。
> *   如果数值为**零**，则表示 *a1* 等于 *a2* 。

下面的程序说明了**小数的使用。比较(十进制，十进制)方法**

**例 1:** 当 a1 大于 a2 时。

```cs
// C# program to demonstrate the
// Decimal.Compare(Decimal, 
// Decimal) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring the decimal variables
        Decimal a1 = 4;
        Decimal a2 = 3;

        // comparing the two Decimal value
        // using Compare() method;
        Decimal value = Decimal.Compare(a1, a2);

        // Display the compare value
        Console.WriteLine("The compare value is : {0}",
                                                value);
    }
}
```

**Output:**

```cs
The compare value is : 1

```

**例 2:** 当 a1 小于 a2 时。

```cs
// C# program to demonstrate the
// Decimal.Compare(Decimal,
// Decimal) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring the decimal variables
        Decimal a1 = 1;
        Decimal a2 = 9;

        // comparing the two Decimal value
        // using Compare() method;
        Decimal value = Decimal.Compare(a1, a2);

        // Display the compare value
        Console.WriteLine("The compare value is : {0}",
                                                value);
    }
}
```

**Output:**

```cs
The compare value is : -1

```

**例 3:** 当 a1 等于 a2 时。

```cs
// C# program to demonstrate the
// Decimal.Compare(Decimal,
// Decimal) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring the decimal variables
        Decimal a1 = 5;
        Decimal a2 = 5;

        // comparing the two Decimal value
        // using Compare() method;
        Decimal value = Decimal.Compare(a1, a2);

        // Display the compare value
        Console.WriteLine("The compare value is : {0}",
                                                value);
    }
}
```

**Output:**

```cs
The compare value is : 0

```