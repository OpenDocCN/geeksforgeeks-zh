# Scala 中的数据类型

> 原文:[https://www.geeksforgeeks.org/data-types-in-scala/](https://www.geeksforgeeks.org/data-types-in-scala/)

数据类型是一种数据分类，它告诉编译器变量具有哪种类型的值。*例如*，如果一个变量有 int 数据类型，那么它保存数值。在 Scala 中，数据类型在长度和存储方面与 Java 相似。在 Scala 中，数据类型被视为相同的对象，因此数据类型的第一个字母是大写字母。
Scala 中可用的数据类型如下表所示:

| 数据类型 | 缺省值 | 描述 |
| 布尔代数学体系的 | 错误的 | 真或假 |
| 字节 | Zero | 8 位有符号值。范围:-128 到 127 |
| 短的 | Zero | 16 位有符号值。范围:-2 <sup>15</sup> 至 2 <sup>15</sup> -1 |
| 茶 | \u000 ' | 16 位无符号 unicode 字符。范围:0 至 2 <sup>16</sup> -1 |
| （同 Internationalorganizations）国际组织 | Zero | 32 位有符号值。范围:-2 <sup>31</sup> 至 2 <sup>31</sup> -1 |
| 长的 | 0L | 64 位有符号值。范围:-2 <sup>63</sup> 至 2 <sup>63</sup> -1 |
| 浮动 | 0.0F | 32 位 IEEE 754 单精度浮点 |
| 两倍 | 0.0D | 64 位 IEEE 754 双精度浮点 |
| 线 | 空 | 一连串的字符 | 单位 | – | 无价值。 | 没有任何东西 | – | 它是所有其他类型的子类型，不包含任何值。 | 任何的 | – | 它是所有其他类型的超类型 | 安雅瓦尔 | – | 它充当值类型。 | 任何参考 | – | 它用作引用类型。 |

**注意:** Scala 不像 Java 那样包含基元类型的概念。

**例如:**

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

**输出:**

```scala
boolean:geeksforgeeks
byte:126
float:2.45673
integer:3
short:45
double:2.93846523
char:A

```

**[Scala 中的文字](https://www.geeksforgeeks.org/scala-literals/) :** 这里我们将讨论 Scala 中使用的不同类型的文字。

*   **整型文字:**一般为整型或长型(使用“L”或“I”后缀)。一些合法的整数文字是:

    > 02
    > 0
    > 40
    > 213
    > 0x ffffffff
    > 0743 l
    > 
    > *   **浮点文字:**这些是浮点型的(使用“F”或“F”后缀)和双精度型的。
    >     
    >     
    >     > 0.7
    >     > 1e 60f
    >     > 3.12154 f
    >     > 1.0e 100
    >     > 3
    >     
    >     *   **布尔文字:**这些都是布尔类型，只包含真和假。*   **符号文字:**在 Scala 中，符号是一个 case 类。在符号文字中，“y”与 scala 相同。符号(“Y”)。
    >     
    >     
    >     > 包斯卡拉
    >     > 最终案例类符号私有(名称:字符串){
    >     > 覆盖 def toString:String = "+name
    >     > }
    >     
    >     *   **字符文字:**在 Scala 中，字符文字是一个用单引号括起来的单个字符。这些字符是可打印的 unicode 字符，也由转义字符描述。下面显示的有效文字很少:
    >     
    >     
    >     > \ b '
    >     > ' a '
    >     > ' \ r '
    >     > ' \ u 0027 '
    >     
    >     *   **字符串文字:**在 Scala 中，字符串文字是括在双引号之间的字符序列。一些有效的文字如下所示:
    >     
    >     
    >     > 欢迎使用\ n geeksforgeeks "
    >     > " \\这是斯卡拉的教程\ \ "
    >     
    >     *   **空值:**在 Scala 中，空值是有标度的。空类型，这是它适应每个引用类型的方式。它表示为引用特殊“空”对象的引用值。*   **多行文字:**在 Scala 中，多行文字是三重引号之间的字符序列。在这一新行中，其他控制字符是有效的。一些有效的多行文字如下所示:
    >     
    >     
    >     > " " "欢迎来到 geeksforgeeks\n
    >     > 这是\n
    >     > scala 编程语言的教程" " " "