# Scala Long ==(x: Int)方法

> 原文:[https://www.geeksforgeeks.org/scala-long-x-int-method/](https://www.geeksforgeeks.org/scala-long-x-int-method/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。如果该值等于 x，则使用 **==(x: Int)** 方法返回真，否则返回假。

> **方法定义–**def = =(x:Int):布尔值
> 
> **返回–**如果该值等于大于 x，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program to explain the working 
// of Long ==(x: Int) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ==(x: Int) function
        val result = (12.toLong).==(8:Int)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
false

```