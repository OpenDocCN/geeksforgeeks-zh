# Double.IsFinite() 方法（C#）

> 原文：[https://www.geeksforgeeks.org/double-isfinite-method-in-c-sharp/](https://www.geeksforgeeks.org/double-isfinite-method-in-c-sharp/)

**Double.IsFinite()** 方法用于检查双精度值是否越界。

## 语法
```csharp
public static bool IsFinite(double value);
```

## 返回值
如果值是有限的，该方法返回 `true`，否则返回 `false`。

下面的程序说明了 `Double.IsFinite()` 方法的使用：

### 例 1
```cs
// C# program to demonstrate the
// Double.IsFinite() Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        double value1 = 10d;

        // using IsFinite() method
        bool value = Double.IsFinite(value1);

        // Displaying the result
        if (value)
            Console.WriteLine("{0} is finite", value1);
        else
            Console.WriteLine("{0} is not finite", value1);
    }
}
```

**输出：**
```cs
10 is finite
```

### 例 2
```cs
// C# program to demonstrate the
// Double.IsFinite() Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        double value1 = Math.Pow(2, 1000000000000);

        // using IsFinite() method
        bool value = Double.IsFinite(value1);

        // Displaying the result
        if (value)
            Console.WriteLine("{0} is finite", value1);
        else
            Console.WriteLine("{0} is not finite", value1);
    }
}
```

**输出：**
```cs
Infinity is not finite
```