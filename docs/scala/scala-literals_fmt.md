# Scala 文字

> 原文: [https://www.geeksforgeeks.org/scala-literals/](https://www.geeksforgeeks.org/scala-literals/)

任何可以赋给变量的常量值都称为文字/常量。`文字`是一系列用于描述代码中常量值的符号。Scala 中有许多类型的文字，即字符文字、字符串文字、多行字符串文字、布尔文字、整数文字和浮点文字。

## 文字的类型

### 整数文字
当在整数的末尾加上后缀 `L` 或 `l` 时，整数文字通常为 `Int` 类型或 `Long` 类型。类型 `Int` 和类型 `Long` 都是整数。

**注:**
- `Int` 类型的范围是从 `-2^31` 到 `2^31-1`。
- `Long` 类型的范围是 `-2^63` 到 `2^63-1`。
- 当一个整数文字有一个超出这个范围的数字时，就会出现编译时错误。

#### 十进制文字
这里，允许的位数是从 0 到 9。

```scala
val x = 37
```

#### 十六进制文字
这里，允许的数字是从 0 到 9，使用的字符是从 a 到 f。我们可以使用大写和小写字符。

```scala
// 十六进制数应该以 0X 或 0x 为前缀。
val x = 0xFFF
```

**示例:**

```scala
// Scala program of integer
// literals

// Creating object
object integer
{
    // Main method
    def main(args: Array[String])
    {
        // decimal-form literal
        val a = 46

        // Hexa-decimal form literal
        val b = 0xfF

        // Displays results in
        // integer form
        println(a)
        println(b)
    }
}
```

**输出:**

```scala
46
255
```

**注:** 字面的八进制形式已经过时。

### 浮点文字
当在末尾添加后缀 `F` 或 `f` 时，此类文字为 `Double` 类型以及 `Float` 类型，我们甚至可以通过添加后缀 `d` 或 `D` 来指定 `Double` 类型。

```scala
val x = 3.14159
```

**示例:**

```scala
// Scala program of floating
// point literals

// Creating object
object double
{
    // Main method
    def main(args: Array[String])
    {
        // decimal-form literal
        val a = 3.156

        // It is also a decimal
        // form of the literal
        val b = 0123.34

        // Displays results
        println(a)
        println(b)
    }
}
```

**输出:**

```scala
3.156
123.34
```

这里，我们不能指定八进制或十六进制形式的文字。

### 字符文字
字符文字是可打印的 Unicode 字符，或由转义序列表示。

```scala
val x = 'b'
// 单引号中的字符文字。
```

```scala
val x = '\u0051'
// 字符文字的 Unicode 表示，
// 此 Unicode 表示 Q。
```

```scala
val x = '\n'
// 字符文字中的转义序列
```

**示例:**

```scala
// Scala program of character
// literal

// Creating object
object literal
{
    // Main method
    def main(args: Array[String])
    {
        // Creating a character literal
        // in single quote
        val x = 'b'

        // uni-code representation of
        // character literal
        val y = '\u0051'

        // Escape sequence in character
        // literals
        val z = '\n'

        // Displays results
        println(x)
        println(y)
        println(z)
    }
}
```

**输出:**

```scala
b
Q

```