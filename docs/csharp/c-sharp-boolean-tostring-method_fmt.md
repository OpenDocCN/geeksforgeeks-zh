# C# 布尔型 `ToString()` 方法

> 原文：`https://www.geeksforgeeks.org/c-sharp-boolean-tostring-method/`

此方法用于将此实例的值转换为其等效的字符串表示形式，即“True”或“False”。

## 语法

```cs
public override string ToString ();
```

## 返回值

如果该实例的值为 `true`，则该方法返回 `"True"`（`TrueString` 属性的值）；如果该实例的值为 `false`，则该方法返回 `"False"`（`FalseString` 属性的值）。

下面的程序说明了 `Boolean.ToString()` 方法的使用。

## 示例 1

```cs
// C# program to demonstrate
// Boolean.ToString()
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // initializing the bool variables
        bool cat = false;
        bool dog = true;

        // getting the value of string property
        string value1 = cat.ToString();
        string value2 = dog.ToString();

        // print the string property
        Console.WriteLine("cat.ToString() returns {0}", value1);
        Console.WriteLine("dog.ToString() returns {0}", value2);
    }
}
```

**输出：**

```cs
cat.ToString() returns False
dog.ToString() returns True
```

## 示例 2

```cs
// C# program to demonstrate
// Boolean.ToString()
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // initializing the bool variables
        bool alpha = false;
        bool beta = true;
        bool gamma = true;
        bool delta = false;
        bool theta = true;

        // calling getValue() method
        getValue(alpha);
        getValue(beta);
        getValue(gamma);
        getValue(delta);
        getValue(theta);
    }

    // defining getValue() method
    public static void getValue(bool variable)
    {
        // getting the value of string property
        string value = variable.ToString();

        // print the string property
        Console.WriteLine("{0}", value);
    }
}
```

**输出：**

```cs
False
True
True
False
True
```

## 注意

XML 区分大小写，XML 规范将 `"true"` 和 `"false"` 识别为有效的布尔值集。如果由 `ToString()` 方法返回的字符串将被写入一个 XML 文件，应先调用 `ToLowerInvariant()` 方法将其转换为小写。

## 参考

*   `https://docs.microsoft.com/en-us/dotnet/api/system.boolean.tostring?view=netframework-4.7.2#System_Boolean_ToString`