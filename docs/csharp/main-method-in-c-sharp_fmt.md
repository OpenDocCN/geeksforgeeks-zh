# C# 中的主要方法

> 原文: [https://www.geeksforgeeks.org/main-method-in-c-sharp/](https://www.geeksforgeeks.org/main-method-in-c-sharp/)

C# 应用程序有一个**入口点**叫做 `Main` 方法。它是第一个在应用程序启动时被调用的方法，并且存在于每个 C# 可执行文件中。应用程序可以是控制台应用程序或窗口应用程序。C# 程序最常见的入口点是 `static void Main()` 或 `static void Main(String []args)`。

## Main()方法的不同声明

下面是 C# 程序中 `Main` 方法的有效声明：

### 1. 带有命令行参数

This can accept n number of array type parameters during the runtime.

**示例:**

```cs
using System;

class GFG {

    // Main Method
    static public void Main(String[] args)
    {
        Console.WriteLine("Main Method");
    }
}
```

**输出:**

```cs
Main Method
```

**主要语法的含义:**

> **static:** 表示没有对象也可以调用 `Main` 方法。
> **public:** 它是访问修饰符，这意味着编译器可以从任何地方执行它。
> **void:** 主方法不返回任何东西。
> **Main():** 是 `Main` 方法的配置名称。
> **String[] args:** 用于接受*零索引命令行参数*。`args` 是用户定义的名称。所以你可以用一个有效的标识符来改变它。`[]` 必须在 `args` 之前，否则编译器会给出错误。

### 2. 不带命令行参数

It is up to the user whether he wants to take command line arguments or not. If there is a need for command-line arguments then the user must specify the command line arguments in the Main method.

**示例:**

```cs
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        Console.WriteLine("Main Method");
    }
}
```

**输出:**

```cs
Main Method
```

### 3. 适用的访问修饰符

`public`, `private`, `protected`, `internal`, `protected internal` 访问修饰符可以与 `Main()` 方法一起使用。`private protected` 访问修饰符不能与它一起使用。

**示例:**

```cs
using System;

class GFG {

    // Main Method
    protected static void Main()
    {
        Console.WriteLine("Main Method");
    }
}
```

**输出:**

```cs
Main Method
```

**示例:**

```cs
using System;

class GFG {

    // Main Method
    private protected static void Main()
    {
        Console.WriteLine("Main Method");
    }
}
```

**编译器错误:**

> 指定了多个保护修饰符

### 4. 不带任何访问修饰符

`Main()` 方法的默认访问修饰符是 `private`。

**示例:**

```cs
using System;

class GFG {

    // Main Method without any
    // access modifier
    static void Main()
    {
        Console.WriteLine("Main Method");
    }
}
```

**输出:**

```cs
Main Method
```

### 5. 修饰符的顺序

用户也可以在 `Main()` 方法中交换 `static` 和适用修饰符的位置。

**示例:**

```cs
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        Console.WriteLine("Main Method");
    }
}
```

**输出:**

```cs
Main Method
```

**示例:**

```cs
using System;

class GFG {

    // Main Method with swapping of modifiers
    static internal void Main()
    {
        Console.WriteLine("Main Method");
    }
}
```

**输出:**

```cs
Main Method
```

### 6. 返回类型

`Main` 方法也可以有整数返回类型。从 `Main()` 方法返回一个整数值会导致程序获取状态信息。从 `Main()` 方法返回的值被视为进程的退出代码。

**示例:**

```cs
using System;

class GFG {

    // Main Method with int return type
    static int Main()
    {
        Console.WriteLine("Main Method");

        // for successful execution of code
        return 0;
    }
}
```

**输出:**

```cs
Main Method
```

**示例:**

```cs
using System;

class GFG {

    // Main Method with int return type
    static int Main(String[] args)
    {
        Console.WriteLine("Main Method");

        // for successful execution of code
        return 0;
    }
}
```

**输出:**

```cs
Main Method
```

## 要点

*   `Main()` 方法是 C# 程序的入口点，从这里开始执行。
*   `Main()` 方法**必须是静态的**，因为是类级别的方法。要在没有任何类实例的情况下调用，它必须是静态的。非静态 `Main()` 方法会产生编译时错误。
*   `Main()` 方法**不能被**覆盖，因为它是静态方法。此外，静态方法不能是虚拟的或抽象的。
*   **`Main()` 方法的重载**是允许的。但在那种情况下，只有一个 `Main()` 方法被视为启动程序执行的入口点。

**示例:** `Main()` 方法的有效重载

```cs
// C# program to demonstrate the
// Valid overloading of Main()
// method
using System;

class GFG {

    // Main method
    // it can also be written as
    // static void Main(String []args)
    static void Main()
    {
        Console.WriteLine("Main Method");
    }

    // overloaded Main() Method
    static void Main(int n)
    {
        Console.WriteLine("Overloaded Main Method");
    }

    // overloaded Main() Method
    static void Main(int x, int y)
    {
        Console.WriteLine("Overloaded Main Method");
    }
}
```

**输出:**

```cs
Main Method
```

**警告:**

> prog.cs(17, 14): warning CS0028: `GFG.Main(int)' has the wrong signature to be an entry point
> prog.cs(23, 14): warning CS0028: `GFG.Main(int, int)' has the wrong signature to be an entry point

**示例:** `Main()` 方法无效重载

```cs
// C# program to demonstrate the
// Invalid overloading of Main()
// method
using System;

class GFG {

    // Main method
    // it can also be written as
    // static void Main()
    static void Main(String[] args)
    {
        Console.WriteLine("Main Method");
    }

    // overloaded Main() Method
    static void Main()
    {
        Console.WriteLine("Overloaded Main Method");
    }
}
```

**编译错误:**

> prog.cs(11, 14): error CS0017: Program `5c56b8183078e496102b7f2662f8b84e.exe' defines more than one entry point: `GFG.Main(string[])'
> prog.cs(17, 14): error CS0017: Program `5c56b8183078e496102b7f2662f8b84e.exe' defines more than one entry point: `GFG.Main()'

*   命令行参数的允许类型在 `Main()` 方法的参数中只有**字符串数组**。
*   `Main()` 方法允许的**返回类型**为 `void`、`int`、`Task` (来自 C# 7.1) 和 `Task<T>` (来自 C# 7.1)。
*   如果 `Main()` 方法的返回类型为 `Task` 或 `Task<T>`，则 `Main()` 方法的声明可能包含 `async` 修饰符。
*   C# 中的库和服务不需要 `Main()` 方法作为入口点。
*   如果不止一个 C# 类包含 `Main()` 方法，那么用户必须用 `/main` 选项编译程序，以指定哪个 `Main()` 方法将是入口点。