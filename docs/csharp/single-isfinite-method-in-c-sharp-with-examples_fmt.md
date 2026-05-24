# Single.IsFinite() 方法（C#）及示例

> 原文：[https://www.geeksforgeeks.org/single-isfinite-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/single-isfinite-method-in-c-sharp-with-examples/)

`Single.IsFinite()` 方法用于检查浮点值是否越界。

## 语法
```csharp
public static bool IsFinite(float value);
```

## 返回值
如果值是有限的，该方法返回 `true`，否则返回 `false`。

以下程序说明了 `Single.IsFinite()` 方法的使用：

### 示例 1
```csharp
// C# program to demonstrate the
// Single.IsFinite() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        float value1 = 1654.268416f;

        // using IsFinite() method
        bool value = Single.IsFinite(value1);

        // Displaying the result
        if (value)
            Console.WriteLine("{0} is finite", value1);
        else
            Console.WriteLine("{0} is not finite", value1);
    }
}
```

**输出：**
```csharp
1654.268 is finite
```

### 示例 2
```csharp
// C# program to demonstrate the
// Single.IsFinite() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        float value1 = (float)Math.Pow(2, 10000000);

        // using IsFinite() method
        bool value = Single.IsFinite(value1);

        // Displaying the result
        if (value)
            Console.WriteLine("{0} is finite", value1);
        else
            Console.WriteLine("{0} is not finite", value1);
    }
}
```

**输出：**
```csharp
Infinity is not finite
```

## 参考
*   [https://docs.microsoft.com/en-us/dotnet/api/system.single.isfinite?view=netstandard-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.single.isfinite?view=netstandard-2.1)