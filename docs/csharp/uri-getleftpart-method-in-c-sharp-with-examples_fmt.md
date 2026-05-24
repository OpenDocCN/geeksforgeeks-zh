# Uri.GetLeftPart() 方法（C#）及示例

> 原文：[https://www.geeksforgeeks.org/uri-getleftpart-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uri-getleftpart-method-in-c-sharp-with-examples/)

`Uri.GetLeftPart()` 方法是一个实例方法，用于根据传递的 `UriPartial` 枚举从给定的 URI 获取指定的部分。

## 语法
```csharp
string Uri.GetLeftPart(UriPartial part);
```

## 参数
*   **part**：代表 `UriPartial` 枚举值，用于指定从 `Uri` 获取哪个部分。

## 返回值
此方法返回一个字符串值，表示 `Uri` 的指定部分。

## 异常
有两种类型的异常：
*   `System.ArgumentException`：如果指定的部分无效。
*   `System.InvalidOperationException`：如果当前 `Uri` 实例不是绝对 URI。

下面的程序说明了 `Uri.GetLeftPart()` 方法的使用：

### 例 1
```csharp
// C# program to demonstrate the 
// Uri.GetLeftPart() Method 
using System;
using System.Globalization;

class GFG {

    // Main Method 
    public static void Main()
    {
        // Declaring and initializing Uri 
        Uri val;

        val = new Uri("https://www.geeksforgeeks.org/data-structure");

        // Use of Uri.GetLeftPart() Method
        // Getting the Authority
        string str = val.GetLeftPart(UriPartial.Authority);

        Console.WriteLine(str);
    }
}
```

**输出：**
```csharp
https://www.geeksforgeeks.org
```

### 例 2
```csharp
// C# program to demonstrate the 
// Uri.GetLeftPart() Method 
using System;
using System.Globalization;

class GFG {

    // Main Method 
    public static void Main()
    {
        // Declaring and initializing Uri 
        Uri val;

        val = new Uri("https://www.geeksforgeeks.org/");

        // Use of Uri.GetLeftPart() Method
        // Getting the Path
        string str1 = val.GetLeftPart(UriPartial.Path);
        Console.WriteLine(str1);

        // Getting the Query
        string str2 = val.GetLeftPart(UriPartial.Query);
        Console.WriteLine(str2);

        // Getting the Scheme
        string str3 = val.GetLeftPart(UriPartial.Scheme);
        Console.WriteLine(str3);
    }
}
```

**输出：**
```csharp
https://www.geeksforgeeks.org/
https://www.geeksforgeeks.org/
https://
```