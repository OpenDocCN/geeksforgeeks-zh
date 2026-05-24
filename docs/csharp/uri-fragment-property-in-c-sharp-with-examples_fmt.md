# Uri.Fragment 属性（C#）

> 原文：[https://www.geeksforgeeks.org/uri-fragment-property-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uri-fragment-property-in-c-sharp-with-examples/)

`Uri.Fragment` 属性是用于获取转义 URI 片段的实例属性。

**语法：**

```cs
public string Fragment { get; }
```

**返回值：** 该属性返回包含任何 URI 片段信息的 `string`。

**异常：** 此属性为相对的 URI 抛出 `InvalidOperationException`，并且仅对绝对的 URIs 有效。

## 示例 1

```cs
// C# program to demonstrate the
// Uri.Fragment property
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        Uri v1 = new Uri("https://www.geeksforgeeks.org/greedy-algorithms/#standardGreedyAlgorithms");

        // using Fragment property
        Console.WriteLine("Uri Fragment: " + v1.Fragment);
    }
}
```

**输出：**

```cs
Uri Fragment: #standardGreedyAlgorithms
```

## 示例 2

```cs
// C# program to demonstrate the
// Uri.Fragment property
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        Uri v1 = new Uri("https://www.geeksforgeeks.org/greedy-algorithms/#approximateGreedyAlgorthms");

        // using Fragment property
        Console.WriteLine("Uri Fragment: " + v1.Fragment);
    }
}
```

**输出：**

```cs
Uri Fragment: #approximateGreedyAlgorthms
```