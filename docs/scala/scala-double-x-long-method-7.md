# Scala Double *(x: Long)方法

> 原文:[https://www.geeksforgeeks.org/scala-double-x-long-method-7/](https://www.geeksforgeeks.org/scala-double-x-long-method-7/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。使用 ***(x: Long)** 方法返回指定的 Double 值和 Long 值的乘积。

> **方法定义–**def *(x:Long)
> 
> 返回–返回该值与 x 的乘积。

**示例#1:**

```scala
// Scala program to explain working of
// Double *(x: Long) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Long) function
        val result = (13.00210.toDouble).*(5:Long)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
65.01050000000001

```