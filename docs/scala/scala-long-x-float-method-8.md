# Scala Long %(x: Float)法

> 原文:[https://www.geeksforgeeks.org/scala-long-x-float-method-8/](https://www.geeksforgeeks.org/scala-long-x-float-method-8/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。当给定的长值除以浮点值时，使用 **%(x:浮点)**方法返回余数。

> **方法定义–**定义百分比(x:浮动)
> 
> **返回–**返回该值除以 x 的余数。

**示例#1:**

```scala
// Scala program to explain the working 
// of Long %(x: Float) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Float) function
        val result = (125.toLong).%(8:Float)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
5.0
```

**例 2:**

```scala
// Scala program to explain the working 
// of Long %(x: Float) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Float) function
        val result = (165.toLong).%(13:Float)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
9.0
```