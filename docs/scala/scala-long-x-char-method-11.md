# Scala Long %(x: Char)法

> 原文:[https://www.geeksforgeeks.org/scala-long-x-char-method-11/](https://www.geeksforgeeks.org/scala-long-x-char-method-11/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。当给定的长值除以字符值时，使用 **%(x:字符)**方法返回余数。

> **方法定义–**def %(x:Char)
> 
> **返回–**返回该值除以 x 的余数。

**示例#1:**

```scala
// Scala program to explain the working 
// of Long %(x: Char) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Char) function
        val result = (100.toLong).%('G':Int)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
29
```

**例 2:**

```scala
// Scala program to explain the working 
// of Long %(x: Char) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Char) function
        val result = (65.toLong).%('A':Char)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
0
```