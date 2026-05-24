# Scala Long(x:Double)法

> 原文:[https://www . geesforgeks . org/Scala-long-x-double-method-10/](https://www.geeksforgeeks.org/scala-long-x-double-method-10/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。利用 **%(x: Double)** 方法，当给定的长数值除以双数值时，返回余数。

> **方法定义–**def %(x:Double)
> 
> **返回–**返回该值除以 x 的余数。

**示例#1:**

```scala
// Scala program to explain the working 
// of Long %(x: Double) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Double) function
        val result = (125.toLong).%(13:Double)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
8.0
```

**例 2:**

```scala
// Scala program to explain the working 
// of Long %(x: Double) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Double) function
        val result = (165.toLong).%(13:Double)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
9.0
```