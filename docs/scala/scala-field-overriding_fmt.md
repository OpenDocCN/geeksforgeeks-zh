# Scala 字段覆盖

> 原文：[https://www.geeksforgeeks.org/scala-field-overriding/](https://www.geeksforgeeks.org/scala-field-overriding/)

## 概述

在任何面向对象的编程语言中，Overriding 都是一种特性，它允许子类提供其某个超类已经提供的方法或字段的特定实现。在 Scala 中，与在 Java 中的重写相比，重写被进一步明确地声明，因为这里两种方法以及*字段*都可以被重写，但是它有一些必须遵守的限制。

## 规则

字段覆盖的规则如下：

*   最重要的规则之一是，当在子类中覆盖超类字段时，必须使用关键字 `override` 或覆盖符号，否则编译器将抛出错误并终止程序的执行。
*   为了用 `override` 覆盖字段，我们只能覆盖在超类和子类中仅用 `val` 关键字声明的变量。
*   字段覆盖不能覆盖 `var`，因为我们可以读取或写入 `var`。

现在，让我们看一些例子来说明这些限制。

## 示例

```scala
// Scala program of Field
// Overriding

// Creating class
class Shapes
{
    // Creating a variable with
    // val keyword
    val description:String = "shape"
}

// Creating a subclass
class shape_1 extends Shapes
{
    // Overriding field using
    // 'override' keyword
    override val description:String ="It is a circle."

    // Defining a method
    def display()
    {
        // Displays output
        println(description)
    }
}

// Creating a subclass
class shape_2 extends Shapes
{
    // overriding field using
    // 'override' keyword
    override val description:String ="It is a square."

    // Defining a method
    def display()
    {
        // Displays output
        println(description)
    }
}

// Creating object
object GfG
{
    // Main method
    def main(args:Array[String])
    {
        // Creating instances for all
        // the sub-classes
        var x = new shape_1()
        var y = new shape_2()

        // Calling methods
        x.display()
        y.display()
    }
}
```

**输出：**

```scala
It is a circle.
It is a square.
```