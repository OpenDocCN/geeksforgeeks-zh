# Scala short /(x: Char): Int

> 原文:[https://www.geeksforgeeks.org/scala-short-x-char-int/](https://www.geeksforgeeks.org/scala-short-x-char-int/)

简言之，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的一个子类型。使用/(x: Char)方法返回对指定 Char 值进行 x 的商运算的结果

> **方法定义:** def /(x: Char): Int
> 
> **返回类型:**返回值为 x 的商。

**示例#1:**

```scala
// Scala program of Short /(x: Char) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short /(x: Char) function 
        val result = (998.toShort)./('C':Char)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
14

```

**例 2:**

```scala
// Scala program of Short /(x: Char) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short /(x: Char) function 
        val result = (-111.toShort)./('G':Char)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
-1

```