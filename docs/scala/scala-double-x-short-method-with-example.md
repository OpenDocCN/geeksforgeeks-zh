# 斯卡拉双人！=(x:短)方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-double-x-short-method-with-example/](https://www.geeksforgeeks.org/scala-double-x-short-method-with-example/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。**！=(x: Short)** 方法用于检查给定的 Double 和 Short 值是否相等。

> **方法定义–**def！=(x: Short):布尔值
> 
> **返回–**如果该值不等于 x，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program to explain working 
// of Double !=(x: Short) function

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Short) function
        val result = (66.00012).toDouble.!= (66:Short)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
true

```