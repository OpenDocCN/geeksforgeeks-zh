# Scala 标识符

> 原文:[https://www.geeksforgeeks.org/scala-identifiers/](https://www.geeksforgeeks.org/scala-identifiers/)

在编程语言中， ***标识符*** 用于识别目的。在 Scala 中，标识符可以是类名、方法名、变量名或对象名。
**例如:**

```scala
class GFG{
    var a: Int = 20
}
object Main {
    def main(args: Array[String]) {
        var ob = new GFG();
    }
}
```

在上面的程序中，我们有 6 个标识符:

*   **GFG:** 类名
*   **a:** 变量名
*   **主:**对象名称
*   **主要:**方法名称
*   **参数:**变量名
*   **ob:** 对象名称

#### 定义 Java Scala 的规则

定义有效的 Scala 标识符有一定的规则。这些规则必须遵守，否则我们会得到一个**编译时错误**。

*   Scala 标识符**区分大小写。**
*   Scala 不允许您使用关键字作为标识符。
*   **保留字**不能像$等一样作为标识符使用。
*   Scala 只允许那些使用以下四种标识符创建的标识符。
*   标识符的长度没有**限制**，但建议仅使用 4-15 个字母的最佳长度。
*   标识符不应以数字**(【0-9】)**开头。例如，“123geeks”不是有效的 Scala 标识符。

**示例:**

## 斯卡拉

```scala
// Scala program to demonstrate
// Identifiers

object Main
{

    // Main method
    def main(args: Array[String])
    {

    // Valid Identifiers
    var `name` = "Siya";
    var _age = 20;
    var Branch = "Computer Science";
    println("Name:" +`name`);
    println("Age:" +_age);
    println("Branch:" +Branch);
    }
}
```

**输出:**

```scala
Name:Siya
Age:20
Branch:Computer Science
```

在上面的示例中，有效的标识符是:

```scala
Main, main, args, `name`, _age, Branch, +
```

关键词是:

```scala
Object, def, var, println
```

#### Scala 标识符的类型

Scala 支持四种类型的标识符:

*   **字母数字标识符:**这些标识符是以字母(大写或小写字母)或下划线开头，后跟字母、数字或下划线的标识符。
    有效字母数字标识符的示例:

```scala
 _GFG, geeks123, _1_Gee_23, Geeks
```

无效字母数字标识符的示例:

```scala
123G, $Geeks, -geeks
```

**示例:**

## 斯卡拉

```scala
// Scala program to demonstrate
// Alphanumeric Identifiers

object Main
{

    // Main method
    def main(args: Array[String])
    {

    // main, _name1, and Tuto_rial are
    // valid alphanumeric identifiers
    var _name1: String = "GeeksforGeeks"
    var Tuto_rial: String = "Scala"

    println(_name1);
    println(Tuto_rial);
    }
}
```

**输出:**

```scala
GeeksforGeeks
Scala
```

*   **运算符标识符:**这些标识符包含一个或多个运算符字符，如+、:、？、~、或#等。
    有效运营商标识符的示例:

```scala
 +, ++ 
```

**示例:**

## 斯卡拉

```scala
// Scala program to demonstrate
// Operator Identifiers

object Main
{

    // Main method
    def main(args: Array[String])
    {

    // main, x, y, and sum are valid
    // alphanumeric identifiers
    var x:Int = 20;
    var y:Int = 10;

    // Here, + is a operator identifier
    // which is used to add two values
    var sum = x + y;
    println("Display the result of + identifier:");
    println(sum);
    }
}
```

**输出:**

```scala
Display the result of + identifier:
30
```

*   **混合标识符:**这些标识符包含字母数字标识符，后跟过程和操作员标识符。
    有效混合标识符的示例:

```scala
 unary_+, sum_= 
```

**示例:**

## 斯卡拉

```scala
// Scala program to demonstrate
// Mixed Identifiers

object Main
{

    // Main method
    def main(args: Array[String])
    {

    // num_+ is a valid mixed identifier
    var num_+ = 20;
    println("Display the result of mixed identifier:");
    println(num_+);
    }
}
```

**输出:**

```scala
Display the result of mixed identifier:
20
```

*   **文字标识符:**这些是那些标识符，其中任意字符串用后勾号(`…号`)括起来。
    有效混合标识符的示例:

```scala
`Geeks`, `name` 
```

**示例:**

## 斯卡拉

```scala
// Scala program to demonstrate
// Literal Identifiers

object Main
{

    // Main method
    def main(args: Array[String])
    {

    // `name` and `age` are valid literal identifiers
    var `name` = "Siya"
    var `age` = 20
    println("Name:" +`name`);
    println("Age:" +`age`);
    }
}
```

**输出:**

```scala
Name:Siya
Age:20
```