# C# `Char.IsLowSurrogate(string, int)` 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-char-islowsurrogatestring-int32-method/](https://www.geeksforgeeks.org/c-sharp-char-islowsurrogatestring-int32-method/)

此方法用于指示字符串中指定位置的 `Char` 对象是否为低代理项。

## 语法

```cs
public static bool IsLowSurrogate (string s, int index);
```

## 参数

- `s`：是一个字符串。
- `index`：是 `s` 中要评估的字符位置。

## 返回值

如果 `s` 参数中指定字符的数值在 `U+DC00` 到 `U+DFFF` 之间，则该方法返回 `true`，否则返回 `false`。

## 异常

- `ArgumentNullException`：如果 `s` 为 `null`。
- `ArgumentOutOfRangeException`：如果 `index` 不在 `s` 的范围内。

## 示例

以下程序说明了 `Char.IsLowSurrogate(string, int)` 方法的使用：

### 示例 1

```cs
// C# program to demonstrate
// Char.IsLowSurrogate(String,
// Int32) Method
using System;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// calling check() Method
            check("1234", 3);
            check("Tsunami", 3);
            check("psyc0lo", 4);

// declaring and initializing string s1
            string s1 = new String(new char[] {'a', 
                        '\uD800', '\uDC00', 'z' });
            check(s1, 2);
        }
        catch (ArgumentNullException e) {

Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (ArgumentOutOfRangeException e) {

Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

// Defining check() method
    public static void check(string s, int i)
    {
        // checking condition
        // using IsLowSurrogate() Method
        bool val = Char.IsLowSurrogate(s, i);

// checking
        if (val)
            Console.WriteLine("String '{0}' contains Low "
                + "Surrogate value at index {1} ",  s, i);

else
            Console.WriteLine("String '{0}' does't contain any Low"
                           + "Surrogate value at index {1}", s, i);

}
}
```

**输出：**

```cs
String '1234' does't contain any LowSurrogate value at index 3
String 'Tsunami' does't contain any LowSurrogate value at index 3
String 'psyc0lo' does't contain any LowSurrogate value at index 4
String 'að??z' contains Low Surrogate value at index 2
```

### 示例 2：适用于 `ArgumentNullException`

```cs
// C# program to demonstrate
// Char.IsLowSurrogate(String,
// Int32) Method
using System;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// calling check() Method
            check("1234", 3);
            check("Tsunami", 3);
            check("psyc0lo", 4);

// declaring and initializing string s1
            string s1 = new String(new char[] {'a',
                        '\uD800', '\uDC00', 'z' });
            check(s1, 2);

Console.WriteLine("");
            Console.WriteLine("s is null");
            check(null, 4);
        }
        catch (ArgumentNullException e) {

Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (ArgumentOutOfRangeException e) {

Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

// Defining check() method
    public static void check(string s, int i)
    {
        // checking condition
        // using IsLowSurrogate() Method
        bool val = Char.IsLowSurrogate(s, i);

// checking
        if (val)
            Console.WriteLine("String '{0}' contains Low "
                  + "Surrogate value at index {1} ",s, i);

else
            Console.WriteLine("String '{0}' does't contain any Low"
                            + "Surrogate value at index {1}",s, i);

}
}
```

**输出：**

```cs
String '1234' does't contain any LowSurrogate value at index 3
String 'Tsunami' does't contain any LowSurrogate value at index 3
String 'psyc0lo' does't contain any LowSurrogate value at index 4
String 'að??z' contains Low Surrogate value at index 2

s is null
Exception Thrown: System.ArgumentNullException
```

### 示例 3：为 `ArgumentOutOfRangeException`

```cs
// C# program to demonstrate
// Char.IsLowSurrogate(String,
// Int32) Method
using System;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// calling check() Method
            check("1234", 3);
            check("Tsunami", 3);
            check("psyc0lo", 4);

// declaring and initializing string s1
            string s1 = new String(new char[] {'a',
                        '\uD800', '\uDC00', 'z' });
            check(s1, 2);

Console.WriteLine("");
            Console.WriteLine("index is less than zero");
            check("null", -4);
        }
        catch (ArgumentNullException e) {

Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (ArgumentOutOfRangeException e) {

Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

// Defining check() method
    public static void check(string s, int i)
    {
        // checking condition
        // using IsLowSurrogate() Method
        bool val = Char.IsLowSurrogate(s, i);

// checking
        if (val)
            Console.WriteLine("String '{0}' contains Low "
                  + "Surrogate value at index {1} ",s, i);

else
            Console.WriteLine("String '{0}' does't contain any Low"
                            + "Surrogate value at index {1}",s, i);

}
}
```

**输出：**

```cs
String '1234' does't contain any LowSurrogate value at index 3
String 'Tsunami' does't contain any LowSurrogate value at index 3
String 'psyc0lo' does't contain any LowSurrogate value at index 4
String 'að??z' contains Low Surrogate value at index 2

index is less than zero
Exception Thrown: System.ArgumentOutOfRangeException
```

## 参考

- [https://docs.microsoft.com/en-us/dotnet/api/system.char.islowsurrogate?view=netframework-4.7.2#System_Char_IsLowSurrogate_System_String_System_Int32_](https://docs.microsoft.com/en-us/dotnet/api/system.char.islowsurrogate?view=netframework-4.7.2#System_Char_IsLowSurrogate_System_String_System_Int32_)