# C# |字符串类

> 原文:[https://www.geeksforgeeks.org/c-sharp-string-class/](https://www.geeksforgeeks.org/c-sharp-string-class/)

在 C# 中， **[字符串](https://www.geeksforgeeks.org/c-string/)** 是一个 Unicode 字符序列或字符数组。

Unicode 字符的范围将是 **U+0000 到 U+FFFF** 。字符数组也被称为文本。所以字符串是文本的表示。字符串由类**系统表示。弦**。
字符串类在*中定义。NET 基类*库。换句话说，字符串对象是*系统的顺序集合。代表字符串的对象。内存中 String 对象的最大大小可以是 *2GB 或约 10 亿个字符*。*

**弦类特征:**

*   *系统。字符串*类是不可变的，即一旦创建，它的状态就不能改变。
*   在 length 属性的帮助下，它提供给定字符串中存在的字符总数。
*   字符串对象可以包含一个空字符，作为字符串长度的一部分。
*   它提供给定字符串中字符的位置。
*   它允许空字符串。空字符串是包含零个字符的字符串对象的有效实例。
*   已声明但尚未赋值的字符串为 null。试图在该字符串上调用方法会引发*空引用异常*。
*   它还支持搜索字符串、比较字符串、测试相等性、修改字符串、字符串规范化、复制字符串等。
*   它还提供了几种创建字符串的方法，如使用构造函数、使用串联等。

#### 构造器

| 构造器 | 描述 |
| **字符串(字符*)** | 将字符串类的新实例初始化为由指向 Unicode 字符数组的指定指针指示的值。 |
| **字符串(Char*，Int32，Int32)** | 将字符串类的新实例初始化为由指向 Unicode 字符数组的指定指针、该数组中的起始字符位置和长度指示的值。 |
| **字符串(Char，Int32)** | 将字符串类的新实例初始化为由重复指定次数的指定 Unicode 字符指示的值。 |
| **字符串(Char[])** | 将字符串类的新实例初始化为由 Unicode 字符数组指示的值。 |
| **字符串(Char[]，Int32，Int32)** | 将字符串类的新实例初始化为由 Unicode 字符数组、该数组中的起始字符位置和长度指示的值。 |
| **字串(SByte*)** | 将字符串类的新实例初始化为由指向 8 位有符号整数数组的指针指示的值。 |
| **字符串(SByte*，Int32，Int32)** | 将字符串类的新实例初始化为由指向 8 位有符号整数数组的指定指针、该数组中的起始位置和长度指示的值。 |
| **字符串(SByte*，Int32，Int32，编码)** | 将字符串类的新实例初始化为由指向 8 位有符号整数数组、该数组中的起始位置、长度和编码对象的指定指针指示的值。 |

**示例:**

```cs
// C# program to demonstrate the creation
// of string using the constructor
using System;
class Geeks {

    // Main Method
    public static void Main()
    {
        char[] chars = { 'G', 'E', 'E', 'K', 'S' };

        // Create a string from a character array.
        string str1 = new string(chars);
        Console.WriteLine(str1);

        // Create a string that consists of
        // a character repeated 5 times.
        string str2 = new string('E', 5);
        Console.WriteLine(str2);
    }
}
```

**Output:**

```cs
GEEKS
EEEEE

```