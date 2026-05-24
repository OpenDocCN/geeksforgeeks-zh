# Scala 双倍(x: Long)法

> 原文:[https://www.geeksforgeeks.org/scala-double-x-long-method-6/](https://www.geeksforgeeks.org/scala-double-x-long-method-6/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。当给定的 Double 值除以 Long 值时，使用 **%(x: Long)** 方法返回余数。

> **方法定义–**def %(x:Long)
> 
> 返回–返回该值除以 x 的余数。

**示例#1:**

```scala
// Scala program to explain the working 
// of Double %(x: Long) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Long) function
        val result = (12.01255.toDouble ).%(8:Long)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
4.012549999999999

```