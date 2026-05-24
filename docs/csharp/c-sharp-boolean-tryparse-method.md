# C# |布尔型。锥虫()法

> 原文:[https://www . geeksforgeeks . org/c-sharp-boolean-tryparse-method/](https://www.geeksforgeeks.org/c-sharp-boolean-tryparse-method/)

此方法用于将逻辑值的指定字符串表示形式转换为其布尔等价形式。它返回一个值，该值指示转换是成功还是失败。

**语法:**

```cs
public static bool TryParse (string value, out bool result);
```

**参数:**

> **值:**是包含要转换的值的字符串。
> 
> **结果:**当此方法返回时，如果转换成功，如果值等于 TrueString 则包含 **true** 如果值等于 FalseString 则包含 **false** 。如果转换失败，则包含 false。如果该值为空或不等于 TrueString 或 FalseString 字段的值，转换将失败。

**返回值:**如果值转换成功，该方法返回*真*，否则返回*假*。

下面的程序说明了**布尔值的使用。**方法:

**例 1:**

```cs
// C# program to demonstrate
// Boolean.TryParse(String, Boolean)
// Method
using System;

class GFG {

// Main Method
public static void Main() {

        // passing different values 
        // to the method to check
        checkParse("true");
        checkParse("false");
        checkParse("'     true     '");
        checkParse(" {content}# xA0; ");
        checkParse("1");
    }

// Declaring checkparse method
public static void checkParse(string value) {

        // Declaring data type
        bool result;
        bool flag;

        // using the method
        result = Boolean.TryParse(value, out flag);

        // Display boolean type result
        Console.WriteLine("{0} --> {1} ", value, result);
    }
}
```

**Output:**

```cs
true --> True 
false --> True 
'     true     ' --> False 
 $   --> False 
1 --> False

```

**例 2:**

```cs
// C# program to demonstrate
// Boolean.TryParse(String, Boolean)
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // passing different values 
        // to the method to check
        checkParse("true1");
        checkParse(null);
        checkParse(String.Empty);
    }

// Declaring checkparse method
public static void checkParse(string value) {

        // Declaring data type
        bool result;
        bool flag;

        // using the method
        result = Boolean.TryParse(value, out flag);

        // Display boolean type result
        Console.WriteLine("{0} --> {1} ", value, result);
    }
}
```

**Output:**

```cs
true1 --> False 
 --> False 
 --> False

```

**注意:**TryParse 方法类似于*解析*方法，只是如果转换失败，TryParse 方法不会抛出异常。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . boolean . tryparse？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.boolean.tryparse?view=netframework-4.7.2)