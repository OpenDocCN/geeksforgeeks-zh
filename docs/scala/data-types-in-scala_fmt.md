# Scala 中的数据类型

> 原文: [https://www.geeksforgeeks.org/data-types-in-scala/](https://www.geeksforgeeks.org/data-types-in-scala/)

数据类型是一种数据分类，它告诉编译器变量具有哪种类型的值。例如，如果一个变量有 `int` 数据类型，那么它保存数值。在 Scala 中，数据类型在长度和存储方面与 Java 相似。在 Scala 中，数据类型被视为相同的对象，因此数据类型的第一个字母是大写字母。

Scala 中可用的数据类型如下表所示：

| 数据类型 | 缺省值 | 描述 |
| :--- | :--- | :--- |
| `Boolean` | `false` | 真或假 |
| `Byte` | `Zero` | 8 位有符号值。范围：-128 到 127 |
| `Short` | `Zero` | 16 位有符号值。范围：-2<sup>15</sup> 至 2<sup>15</sup> -1 |
| `Char` | `\u0000` | 16 位无符号 unicode 字符。范围：0 至 2<sup>16</sup> -1 |
| `Int` | `Zero` | 32 位有符号值。范围：-2<sup>31</sup> 至 2<sup>31</sup> -1 |
| `Long` | `0L` | 64 位有符号值。范围：-2<sup>63</sup> 至 2<sup>63</sup> -1 |
| `Float` | `0.0F` | 32 位 IEEE 754 单精度浮点 |
| `Double` | `0.0D` | 64 位 IEEE 754 双精度浮点 |
| `String` | `null` | 一连串的字符 |
| `Unit` | – | 无价值。 |
| `Null` | – | 它是所有其他类型的子类型，不包含任何值。 |
| `Any` | – | 它是所有其他类型的超类型 |
| `AnyVal` | – | 它充当值类型。 |
| `AnyRef` | – | 它用作引用类型。 |

`注意:` Scala 不像 Java 那样包含基元类型的概念。

`例如:`

```scala
// Scala program to illustrate Datatypes
object Test
{
    def main(args: Array[String])
    {
        var a: Boolean = true
        var a1: Byte = 126
        var a2: Float = 2.45673f
        var a3: Int = 3
        var a4: Short = 45
        var a5: Double = 2.93846523
        var a6: Char = 'A'
        if (a == true)
        {
            println("boolean:geeksforgeeks")
        }
        println("byte:" + a1)
        println("float:" + a2)
        println("integer:" + a3)
        println("short:" + a4)
        println("double:" + a5)
        println("char:" + a6)
    }
}
```

`输出:`

```scala
boolean:geeksforgeeks
byte:126
float:2.45673
integer:3
short:45
double:2.93846523
char:A
```

# [Scala 中的文字](https://www.geeksforgeeks.org/scala-literals/)

这里我们将讨论 Scala 中使用的不同类型的文字。

## 整型文字
一般为整型或长型（使用“L”或“l”后缀）。一些合法的整数文字是：

```
02
0
40
213
0xFFFFFFFF
0743L
```

## 浮点文字
这些是浮点型的（使用“F”或“f”后缀）和双精度型的。

```
0.7
1e60f
3.12154f
1.0e100
3.0
```

## 布尔文字
这些都是布尔类型，只包含 `true` 和 `false`。

## 符号文字
在 Scala 中，符号是一个 `case` 类。在符号文字中，`'y` 与 `scala.Symbol("Y")` 相同。

```scala
package scala
final case class Symbol private (name: String) {
  override def toString: String = "'" + name
}
```

## 字符文字
在 Scala 中，字符文字是一个用单引号括起来的单个字符。这些字符是可打印的 unicode 字符，也由转义字符描述。下面显示的有效文字很少：

```
'\b'
'a'
'\r'
'\u0027'
```

## 字符串文字
在 Scala 中，字符串文字是括在双引号之间的字符序列。一些有效的文字如下所示：

```
"Welcome to \n geeksforgeeks"
"\\\\ This is a tutorial on Scala \\\\"
```

## 空值
在 Scala 中，空值是 `Null` 类型，这是它适应每个引用类型的方式。它表示为引用特殊 `null` 对象的引用值。

## 多行文字
在 Scala 中，多行文字是三重引号之间的字符序列。在这一新行中，其他控制字符是有效的。一些有效的多行文字如下所示：

```
"""Welcome to geeksforgeeks
This is
a tutorial on Scala programming language"""
```