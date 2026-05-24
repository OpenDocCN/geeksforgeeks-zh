# C# | `Char.GetHashCode()` 方法示例

> 原文：[https://www.geeksforgeeks.org/c-sharp-char-gethashcode-method-with-examples/](https://www.geeksforgeeks.org/c-sharp-char-gethashcode-method-with-examples/)

此方法用于返回此实例的哈希代码。

## 语法

```cs
public override int GetHashCode();
```

## 返回值

这个方法返回一个 32 位有符号整数哈希码。

以下程序说明了 `Char.GetHashCode()` 方法的使用：

### 例 1

```cs
// C# program to demonstrate
// Char.GetHashCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // declaring and initializing char
        char ch1 = 'B';

        // checking condition
        // using Equals() Method
        int val = ch1.GetHashCode();

        // Display Hashcode
        Console.WriteLine("Hashcode :- {0}", val);
    }
}
```

**输出：**

```cs
Hashcode :- 4325442
```

### 例 2

```cs
// C# program to demonstrate
// Char.GetHashCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // calling hash() Method
        hash('a');
        hash('b');
        hash('c');
        hash('x');
        hash('y');
        hash('z');
    }

    // Defining hash() Method
    public static void hash(char ch)
    {
        // checking condition
        // using Equals() Method
        int val = ch.GetHashCode();

        // Display Hashcode
        Console.WriteLine("Hashcode of " + ch +
                          " :- {0}", val);
    }
}
```

**输出：**

```cs
Hashcode of a :- 6357089
Hashcode of b :- 6422626
Hashcode of c :- 6488163
Hashcode of x :- 7864440
Hashcode of y :- 7929977
Hashcode of z :- 7995514
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.char.gethashcode?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.char.gethashcode?view=netframework-4.7.2)