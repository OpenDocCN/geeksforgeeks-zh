# Scala Long %(x: Int)法

> 原文:[https://www.geeksforgeeks.org/scala-long-x-int-method-11/](https://www.geeksforgeeks.org/scala-long-x-int-method-11/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。当给定长值除以整数值时，使用 **%(x: Int)** 方法返回余数。

> **方法定义–**def %(x:Int)
> 
> **返回–**返回该值除以 x 的余数。

**示例#1:**

```scala
// Scala program to explain the working 
// of Long %(x: Int) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Int) function
        val result = (100.toLong).%(3:Int)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
1
```

**例 2:**

```scala
// Scala program to explain the working 
// of Long %(x: Int) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Int) function
        val result = (165.toLong).%(13:Int)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
9
```