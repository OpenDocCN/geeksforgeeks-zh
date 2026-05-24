# C# | Char 结构

> 原文:[https://www.geeksforgeeks.org/c-sharp-char-struct/](https://www.geeksforgeeks.org/c-sharp-char-struct/)

在 C# 中，Char Struct 用于将字符表示为 UTF-16 代码单元。该结构在*系统*命名空间下定义。基本上，这是用来表示*中的 Unicode 字符。NET* 框架。Unicode 标准使用一个称为**码位**的唯一 21 位标量数字来标识每个 Unicode 字符。它还定义了 UTF-16 编码形式，规定了如何将一个代码点编码成一个或多个 16 位值的序列。每个 16 位值的范围从十六进制 *0x0000 到 0xFFFF* ，并存储在 *Char* 结构中。Char 对象的值是它的 16 位数字(序数)值。
Char 结构提供了不同的方法，用于将当前 Char 对象的值转换为另一种类型的对象，比较 Char 对象，以及检查 Char 对象的 Unicode 类别等。

**字段:**

*   *最大值*:这是一个常量字段，代表一个字符的最大可能值。
*   *最小值*:它是一个常量字段，代表一个字符的最小可能值。

#### 方法

| 方法 | 描述 |
| **[【共享()](https://www.geeksforgeeks.org/c-char-compareto-method/)** | 将此实例与指定的对象或值类型进行比较，并指示此实例是在指定的对象或值类型之前、之后还是在排序顺序中出现在相同的位置。 |
| **[convertfrommutf32(Int32)](https://www.geeksforgeeks.org/c-char-convertfromutf32int32-method/)** | 将指定的 Unicode 代码点转换为 UTF-16 编码字符串。 |
| **converttoft 32()** | 将 UTF-16 编码的代理项对的值转换为 Unicode 代码点。 |
| **[等于()](https://www.geeksforgeeks.org/c-char-equals-method/)** | 返回一个值，该值指示此实例是否等于指定的对象或字符值。 |
| **[GethashCode（）](https://www.geeksforgeeks.org/c-char-gethashcode-method-with-examples/)** | 返回此实例的哈希代码。 |
| **[【get numeric value()](https://www.geeksforgeeks.org/c-char-getnumericvalue-method/)** | 将指定的 Unicode 数字字符转换为双精度浮点数。 |
| **[【gettype code()](https://www.geeksforgeeks.org/c-char-gettypecode-method-with-examples/)** | 返回值类型 Char 的类型代码。 |
| **[【getunicocode category()](https://www.geeksforgeeks.org/c-char-getunicodecategorystring-int32-method-with-examples/)** | 将 Unicode 字符分类到由其中一个 Unicode 类别值标识的组中。 |
| **[【is control()](https://www.geeksforgeeks.org/c-char-iscontrolstring-int32-method/)** | 指示指定的 Unicode 字符是否被归类为控制字符。 |
| **[【isdigt()](https://www.geeksforgeeks.org/c-char-isdigit-method/)** | 指示 Unicode 字符是否归类为十进制数字。 |
| **[【石盐代用品()](https://www.geeksforgeeks.org/c-char-ishighsurrogatestring-int32-method/)** | 指示指定的 Char 对象是否是高代理。 |
| **[IsLetter（）](https://www.geeksforgeeks.org/c-char-isletter-method/)** | 指示 Unicode 字符是否被归类为 Unicode 字母。 |
| **[【islegitimate()](https://www.geeksforgeeks.org/c-char-isletterordigit-method/)** | 指示 Unicode 字符是归类为字母还是十进制数字。 |
| **[【岛电()](https://www.geeksforgeeks.org/c-char-islower-method/)** | 指示 Unicode 字符是否被归类为小写字母。 |
| **[【isowsurrogate()](https://www.geeksforgeeks.org/c-char-islowsurrogatestring-int32-method/)** | 指示指定的 Char 对象是否是低代理。 |
| **[IsNumber（）](https://www.geeksforgeeks.org/c-char-isnumber-method/)** | 指示 Unicode 字符是否被归类为数字。 |
| **[ispentation()](https://www.geeksforgeeks.org/c-char-ispunctuation-method/)** | 指示 Unicode 字符是否被归类为标点符号。 |
| **[【拆分器()](https://www.geeksforgeeks.org/c-char-isseparator-method/)** | 指示 Unicode 字符是否被归类为分隔符。 |
| **[发布](https://www.geeksforgeeks.org/c-char-issurrogatestring-int32-method/)** | 指示字符是否有代理代码单元。 |
| **[问题](https://www.geeksforgeeks.org/c-char-issurrogatepairstring-int32-method/)** | 指示两个指定的字符对象是否形成代理项对。 |
| **[这个符号()](https://www.geeksforgeeks.org/c-char-issymbol-method/)** | 指示 Unicode 字符是否被归类为符号字符。 |
| **[【ispers()](https://www.geeksforgeeks.org/c-char-isupper-method/)** | 指示 Unicode 字符是否被归类为大写字母。 |
| **[【is white space()](https://www.geeksforgeeks.org/c-char-iswhitespace-method/)** | 指示 Unicode 字符是否被归类为空白。 |
| **[解析(字符串)](https://www.geeksforgeeks.org/c-char-parsestring-method/)** | 将指定字符串的值转换为其等效的 Unicode 字符。 |
| tolpower() | 将 Unicode 字符的值转换为其小写等效字符。 |
| **[至](https://www.geeksforgeeks.org/c-char-tolowerinvariantchar-method/)** | 使用不变区域性的大小写规则，将 Unicode 字符的值转换为其小写等效字符。 |
| **[ToString()](https://www.geeksforgeeks.org/c-char-tostring-method/)** | 将此实例的值转换为其等效的字符串表示形式。 |
| **ToUpper()** | 将 Unicode 字符的值转换为其大写等效字符。 |
| **[to pperinvariant(Char)](https://www.geeksforgeeks.org/c-char-toupperinvariantchar-method/)** | 使用不变区域性的大小写规则，将 Unicode 字符的值转换为其大写等效字符。 |
| **尝试(字符串、Char)** | 将指定字符串的值转换为其等效的 Unicode 字符。返回代码指示转换是成功还是失败。 |

**例 1:**

```cs
// C# program to demonstrate the
// Char.CompareTo(Char) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        char c1 = 'G';
        char c2 = 'f';
        char c3 = 'M';

        // using Char.CompareTo(Char) Method
        // returns 0 as this instance has
        // same position in the sort as in c1
        Console.WriteLine('G'.CompareTo(c1));

        // using Char.CompareTo(Char) Method
        // returns -31 as this instance
        // precedes c2
        Console.WriteLine('G'.CompareTo(c2));

        // using Char.CompareTo(Char) Method
        // returns -6 as this instance follows
        // c3
        Console.WriteLine('G'.CompareTo(c3));
    }
}
```

**输出:**

```cs
0
-31
-6

```

**例 2:**

```cs
// C# program to illustrate the
// Char.IsWhiteSpace(Char) Method
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Declaration of data type
        bool output;

        // checking if space
        // is a whitespace
        char c1 = ' ';
        output = Char.IsWhiteSpace(c1);
        Console.WriteLine(output);

        // checking if carriage return
        // is a whitespace
        char c2 = '\n';
        output = Char.IsWhiteSpace(c2);
        Console.WriteLine(output);

        // checking if hyphen
        // is a whitespace
        char c3 = '-';
        output = Char.IsWhiteSpace(c3);
        Console.WriteLine(output);
    }
}
```

**输出:**

```cs
True
True
False

```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.char?视图= net framework-4 . 7 . 2 # 定义](https://docs.microsoft.com/en-us/dotnet/api/system.char?view=netframework-4.7.2# definition)