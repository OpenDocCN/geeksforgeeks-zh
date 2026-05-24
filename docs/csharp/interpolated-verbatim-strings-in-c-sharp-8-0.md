# C # 8.0 中的插值逐字字符串

> 原文:[https://www . geesforgeks . org/interpoled-逐字-strings-in-c-sharp-8-0/](https://www.geeksforgeeks.org/interpolated-verbatim-strings-in-c-sharp-8-0/)

#### 前提条件:字符串插值和[逐字字符串](https://www.geeksforgeeks.org/c-sharp-verbatim-string-literal/)

在 C# 8.0 之前，您可以一起使用字符串插值($)和逐字标识符(@)，但要按照特定的顺序。这意味着当您同时使用$ token 和@ token 时，$ token 必须出现在@ token 之前。如果您在$ token 之前使用@ token，那么编译器会给您一个错误，如下例所示:

**例 1:**

```cs
// C# program to illustrate the use
// of interpolated verbatim strings
using System;

class GFG {

    // Main Method
    static void Main()
    {
        int Base = 10;
        int Height = 30;
        int area = (Base * Height) / 2;

        // Here, $ token appears before @ token
        Console.WriteLine("Finding the area of a triangle:");
        Console.WriteLine($@"Height = ""{Height}"" and Base = ""{Base}""");
        Console.WriteLine($@"Area = ""{area}""");
    }
}
```

**输出:**

```cs
Finding the area of a triangle:
Height = "30" and Base = "10"
Area = "150"

```

**例 2:**

```cs
// C# program to illustrate the use 
// of interpolated verbatim strings
using System;

class GFG {

    // Main Method
    static void Main()
    {
        int Base = 10;
        int Height = 30;
        int area = (Base * Height) / 2;

        // Here, @ token appears before $ token
        // But the compiler will give an error
        Console.WriteLine("Finding the area of a triangle:");
        Console.WriteLine(@ {content}quot;Height = ""{Height}"" and Base = ""{Base}""");                   
        Console.WriteLine(@ {content}quot;Area = ""{area}""");
    }
}
```

**错误:**

> 错误 CS1646:逐字说明符后需要关键字、标识符或字符串:@
> 错误 CS1646:逐字说明符后需要关键字、标识符或字符串:@

当我们在$ token 之前使用@ token 时，编译器会给出一个错误。这个问题在 C# 8.0 中得到了解决，现在您可以在$ token 之前使用@ token，或者在@ token 之前使用$ token

```cs
$@"..."
Or
@{content}quot;..."

```

编译器不会给出错误。如下例所示:

**示例:**

```cs
// C# program to illustrate the use
// of interpolated verbatim strings
using System;

namespace Geeks {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        int Base = 40;
        int Height = 80;
        int area = (Base * Height) / 2;
        Console.WriteLine("Finding the area of a triangle:");

        // Here, $ token appears before @ token
        Console.WriteLine($@"Height = ""{Height}"" and Base = ""{Base}""");

        // Here, @ token appears before $ token
        Console.WriteLine(@{content}quot;Area = ""{area}""");
    }
}
}
```

**输出:**

```cs
Finding the area of a triangle:
Height = "80" and Base = "40"
Area = "1600"

```