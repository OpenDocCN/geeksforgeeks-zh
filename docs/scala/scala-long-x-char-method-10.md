# Scala Long *(x: Char)方法

> 原文:[https://www.geeksforgeeks.org/scala-long-x-char-method-10/](https://www.geeksforgeeks.org/scala-long-x-char-method-10/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。使用 ***(x: Char)** 方法返回指定的 Long 值和 Char 值的乘积。

> **方法定义–**def *(x:Char)
> 
> **返回–**返回该值与 x 的乘积。

**示例#1:**

```scala
// Scala program to explain working of
// Long *(x: Char) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Char) function
        val result = (10.toLong).*('A':Char)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
650
```

**例 2:**

```scala
// Scala program to explain working of
// Long *(x: Char) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Char) function
        val result = (150.toLong).*('G':Char)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
10650
```