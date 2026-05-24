# C# |文字

> 原文:[https://www.geeksforgeeks.org/c-sharp-literals/](https://www.geeksforgeeks.org/c-sharp-literals/)

固定值称为**。文字是变量使用的值。值可以是整数、浮点数或字符串等。**

```cs
// Here 100 is a constant/literal.
int x = 100; 
```

**文字可以是以下类型:**

***   **Integer text***   **Floating-point text***   **Character text***   **String text***   **Empty text***   **Boolean****

****整数文字:**整数类型的文字称为整数文字。它可以是八进制、十进制、二进制或十六进制常量。十进制数字不需要前缀。后缀也可以与整数文字一起使用，如 *U* 或 *u* 用于无符号数字，而 *l* 或 *L* 用于长数字。默认情况下，每个文字都是 int 类型的。对于整型数据类型(字节、短整型、整型、长整型)，我们可以通过以下方式指定文字:**

***   **Decimal character (radix 10):** In this form, the allowed number of digits is 0-9.**

```cs
int x = 101;

```

*   **Octal character (radix 8):** In this form, the allowed number of digits is 0-7.

```cs
// The octal number should be prefix with 0.
int x = 0146; 

```

*   **Six decimal characters (base16):** In this form, the allowed numbers are 0-9 and the characters are A-F. We can use both uppercase and lowercase characters. As we know, c# is a case-sensitive programming language, but here c# is case-insensitive.

```cs
// The hexa-decimal number should be prefix
// with 0X or 0x.
int x = 0X123Face; 

```

*   **Binary characters (radix 2):** In this form, only of **1 and** of **0 are allowed.**

```cs
// The binary number should be prefix with 0b.
int x = 0b101

```

**例:**

```cs
07778    // invalid: 8 is not an octal digit 
045uu    // invalid: suffix (u) is repeated
0b105    // invalid: 5 is not a binary digit
0b101    // valid binary literal
456      // valid decimal literal
02453    // valid octal literal 
0x65d    // valid hexadecimal literal 
12356    // valid int literal 
304U     // valid unsigned int literal 
3078L    // valid long literal 
965UL    // valid unsigned long literal 

```

**程序:**

## C#

```cs
// C# program to illustrate the use of Integer Literals
using System;

class Geeks{

    // Main method
    public static void Main(String[] args)
    {

        // decimal-form literal
        int a = 101;

        // octal-form literal
        int b = 0145;

        // Hexa-decimal form literal
        int c = 0xFace;

        // binary-form literal
        int x = 0b101;

        Console.WriteLine(a);
        Console.WriteLine(b);
        Console.WriteLine(c);
        Console.WriteLine(x);
    }
}
```

```cs
101
145
64206
5

```

**浮点文字:**具有整数部分、小数点、小数部分和指数部分的文字称为浮点文字。这些可以用十进制或指数形式表示。

**例:**

```cs
Double d = 3.14145       // Valid
Double d = 312569E-5      // Valid
Double d = 125E             // invalid: Incomplete exponent 
Double d = 784f            // valid
Double d = .e45           // invalid: missing integer or fraction

```

**程序:**

## c#

```cs
// C# program to illustrate the use of
// floating-point literals
using System;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {
        // decimal-form literal
        double a = 101.230;

        // It also acts as decimal literal
        double b = 0123.222;

        Console.WriteLine(a);
        Console.WriteLine(b);
    }
}
```

**输出:**

```cs
101.23
123.222

```

**注意:**默认情况下，每个浮点文字都是双精度类型，因此我们不能直接赋值给浮点变量。但是我们可以通过以 f 或 f 为后缀将浮点文字指定为浮点类型，我们可以通过以 D 或 D 为后缀将浮点文字明确指定为双精度类型，当然，这种约定不是必需的。

**字符文字:**对于字符数据类型，我们可以通过 3 种方式指定文字:

*   **Single quotation mark:** We can specify the text as the character data type within the single quotation mark.

```cs
char ch = 'a';

```

*   **Unicode representation:** We can specify the character' \ uxxxx' in the Unicode representation. Xxxx here represents four hexadecimal numbers.

```cs
char ch = '\u0061';// Here /u0061 represent a.

```

*   **Escape sequence:** Each escape character can be designated as a character literal.

```cs
char ch = '\n';

```

<figure class="table">

| 换码顺序 | 意为 |
| --- | --- |
| \\ | \人物 |
| \' | '人物 |
| \？ | ？人物 |
|  | 【人物 |
| \b | 退格 |
| \a | 警报或铃声 |
| \n | 新线 |
| \f | 表格提要 |

</figure>

**例:**

## c#

```cs
// C# program to illustrate the use of char literals
using System;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // character literal within single quote
        char ch = 'a';

        // Unicode representation
        char c = '\u0061';

        Console.WriteLine(ch);
        Console.WriteLine(c);

        // Escape character literal
        Console.WriteLine("Hello\n\nGeeks\t!");
    }
}
```

```cs
a
a
Hello

Geeks    !

```

**字符串文字:**包含在**双引号(" "**中或以 **@""** 开头的文字称为字符串文字。

**例:**

```cs
String s1 = "Hello Geeks!";

String s2 = @"Hello Geeks!";

```

**程序:**

## c#

```cs
// C#  program to illustrate the use of String literals
using System;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        String s = "Hello Geeks!";
        String s2 = @"Hello Geeks!";

        // If we assign without "" then it
        // treats as a variable
        // and causes compiler error
        // String s1 = Geeks;

        Console.WriteLine(s);
        Console.WriteLine(s2);
    }
}
```

**输出:**

```cs
Hello Geeks!
Hello Geeks!

```

**布尔文字:**布尔文字只允许有两个值，即真和假。

**例:**

```cs
bool b = true;
bool c = false;

```

**程序:**

## c#

```cs
// C# program to illustrate the use
// of boolean literals
using System;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {
        bool b = true;
        bool c = false;

        // these will give compile time error
        // bool d = 0;
        // bool e = 1;
        // Console.WriteLine(d);
        // Console.WriteLine(e);

        Console.WriteLine(b);
        Console.WriteLine(c);
    }
}
```

**输出:**

```cs
True
False

```**