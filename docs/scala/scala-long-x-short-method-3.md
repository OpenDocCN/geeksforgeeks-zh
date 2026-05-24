# 斯卡拉长< =(x:短)法

> 原文:[https://www.geeksforgeeks.org/scala-long-x-short-method-3/](https://www.geeksforgeeks.org/scala-long-x-short-method-3/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。如果该值小于或等于 x，则使用 **< (x: Short)** 方法返回真，否则返回假。

> **方法定义–**定义< =(x:短):布尔值
> 
> **返回–**如果该值小于或等于 x，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program to explain the working 
// of Long <=(x: Short) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <=(x: Short) function
        val result = (12.toLong).<=(15:Short)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```