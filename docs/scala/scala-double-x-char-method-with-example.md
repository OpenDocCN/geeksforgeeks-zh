# 斯卡拉双人！=(x: Char)方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-double-x-char-method-with-example/](https://www.geeksforgeeks.org/scala-double-x-char-method-with-example/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。**！=(x: Char)** 方法用于检查给定的 Double 和 Char 值是否相等。

> **方法定义–**def！=(x: Char):布尔值
> 
> **返回–**如果该值不等于 x，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program to explain working 
// of Double !=(x: Char) function

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Char) function
        val result = (66.01230).toDouble.!= ('B':Char)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
true

```